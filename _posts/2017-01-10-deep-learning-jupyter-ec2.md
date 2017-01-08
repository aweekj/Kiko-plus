---
published: true
author: min
title: A Lazy Girl's Guide to Setting Up Jupyter on EC2 for Deep Learning
tags: 
    - python
    - jupyter
    - aws
---
**TL;DR**: _I describe how I set up a Jupyter server on EC2 with a Marketplace AMI (so we don't have to install too much stuff ourselves) so we can speed up the training of our NN without leaving the convenient workflow of a Jupyter notebook._

Getting started with deep learning is quite easy these days given all the available material out there. I got inspired to build my first convolutional neural network for sentiment analysis after reading [this paper](https://arxiv.org/abs/1408.5882) by Kim (2014) and attending a [PyData meetup](http://www.slideshare.net/textkernel/practical-deep-learning-for-nlp) with a `keras` demo (more about this maybe in another post). 

Given the experimental nature of my enterprise I started out directly in a Jupyter notebook running locally on my Mac. However, after building more and more layers with more and more filters and starting to tune the hyperparameters for my networks, I noticed that the training time is starting to slow me down. Hence, it was time to move to an AWS EC2 machine with a dedicated GPU to speed up my experiments. In the following I will describe the steps I took to get to the point of training a NN with `keras` in a Jupyter notebook running on an EC2 instance. 

**Requirements**: I assume in this post you already know how to set up an EC2 instance with your credentials so that you can access the instance once it has booted up. I also assume you know how to work with virtual environments for Python and you know the general workflow of installing Python packages. If not you can easily find [some](https://realpython.com/blog/python/python-virtual-environments-a-primer/) [articles](http://www.simononsoftware.com/virtualenv-tutorial-part-2/) explaining the purpose of virtual environments.


### 1. Launch an EC2 Instance With a Suitable AMI

Choosing the right AMI (Amazon Machine Image) will save us a lot of installation effort and time. Since our goal is to do some deep learning, I suggest looking for an AMI that comes with the deep learning library of your desire. In my case I wanted to use either `tensorflow` or `keras` with a `tensorflow` backend. Some searching in the AWS Marketplace reveals that [Amazon's Deep Learning AMI](https://aws.amazon.com/marketplace/pp/B01M0AXXQB) and [Bitfusion Ubuntu 14 TensorFlow AMI](https://aws.amazon.com/marketplace/pp/B01EYKBEQ0) are nice options. In the end I opted for the Amazon AMI and installed `keras` myself (see next step). Jupyter is also already preinstalled on both. 

(If you are not sure yet which libraries you will need, you can also use a vanilla Linux AMI and install everything you need later on the command line. But since this is the lazy girl's guide we want to spend as little time as possible on installation of tools.)

After choosing the AMI we also need to choose the right instance type. Reasonable choices are the g2 and p2 instances, both of which have dedicated GPUs. I opted for a p2 machine, since they are [newer](https://aws.amazon.com/blogs/aws/new-p2-instance-type-for-amazon-ec2-up-to-16-gpus/) and basically [designed for the best deep learning performance](http://www.bitfusion.io/2016/11/03/quick-comparison-of-tensorflow-gpu-performance-on-aws-p2-and-g2-instances/).

I leave all other launch options to their default values, apart from the security group definitions. Here we need to make some changes as we want to be able to access the Jupyter server from our browser via HTTPS later on.

| Type		| Protocol	| Port Range	| Source |
|-----------|-----------|---------------|--------|
| HTTPS		| TCP		| 443			|0.0.0.0/0 |
| SSH		| TCP		| 22			|0.0.0.0/0|
| Custom TCP Rule	|TCP	|8888		|0.0.0.0/0|


### 2. Set up the Environment on the Remote Machine

If the chosen AMI contains all the libraries you need you can skip this step. In my case I had to install `keras` myself, which was quite easy with to do with `pip`. Let's ssh to the instance.

```shell
ssh -i ~/.ssh/min.pem ec2-user@ec2-xx-xxx-xx-xxx.eu-west-1.compute.amazonaws.com
```

In the case of the Amazon Deep Learning AMI everything is installed in `~/src/`. I first activate the default `conda` environment named `root` and install `keras` into that environment. 

```shell
source src/anaconda3/bin/activate root
pip install keras
```

Note that I activated the Anaconda 3 default environment, which by default uses Python 3.5. If you prefer to use Python 2.7 (but why?), you can do the same thing with the preinstalled Anaconda 2 distribution in `src/anaconda2`. 


### 3. Configure the Jupyter Server

We will now generate the configuration file for our Jupyter server. Since we are using HTTPS we have to create a certificate first. We will use Python to generate a key based on a password you can choose for yourself. We will tell the server that this password will be required to access the notebooks. 

Or: just execute the commands given below, follow the instructions on the command line (for the very lazy ones: you can also leave all the prompts empty) and things will just magically work.

```shell
jupyter notebook --generate-config
key=$(python -c "from notebook.auth import passwd; print(passwd())")
```

```shell
cd ~
mkdir certs
cd certs
certdir=$(pwd)
openssl req -x509 -nodes -days 365 -newkey rsa:1024 -keyout mycert.key -out mycert.pem
```

```shell
cd ~
sed -i "1 a\
c = get_config()\\
c.NotebookApp.certfile = u'$certdir/mycert.pem'\\
c.NotebookApp.keyfile = u'$certdir/mycert.key'\\
c.NotebookApp.ip = '*'\\
c.NotebookApp.open_browser = False\\
c.NotebookApp.password = u'$key'\\
c.NotebookApp.port = 8888" .jupyter/jupyter_notebook_config.py
```


### 4. Run the Jupyter Server

Before starting the server, it is advisable to use some kind of session management tool to keep the server running after a user logout. I usually use `screen` but here also you can choose whichever tool you like.

```shell
screen -S jupyter
mkdir notebook
cd notebook
jupyter notebook
```

If you want to test the server with a notebook of yours immediately, now would be a good time to copy a notebook over to the server with `scp`. If you don't have one at hand, you could copy an [example notebook](https://github.com/fchollet/keras/tree/master/examples) from the `keras` repository. 

Your Jupyter server should now be accessible in your browser with this URL: `https://<your-instances-public-ip>:8888`. Try it!


### 5. Have Fun Experimenting with NNs

We're done! Have fun with your notebooks!

The only thing I still had to do is to make `keras` use `tensorflow` as the backend library by modifying the config file `~/.keras/keras.json` (you have to create it if it isn't already there). Or just stick with the `theano` backend, which is also already installed. 

```json
{
    "image_dim_ordering": "tf",
    "epsilon": 1e-07,
    "floatx": "float32",
    "backend": "tensorflow"
}
```

The first time you import `keras`, the console should tell you which backend you are currently using as well as some output indicating that you are using the GPU via CUDA. 
