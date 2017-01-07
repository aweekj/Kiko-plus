---
published: false
---
## A Lazy Girl's Guide to Setting Up Deep Learning in Jupyter on EC2

**TL;DR**: _I describe how I set up a Jupyter server on EC2 with a Marketplace AMI (so we don't have to install too much stuff ourselves) so we can speed up the training of our NN without leaving the convenient workflow of a Jupyter notebook._

Getting started with deep learning is quite easy these days given all the available material out there. I got inspired to build my first convolutional neural network for sentiment analysis after reading [this paper](https://arxiv.org/abs/1408.5882) by Kim (2014) and attending a [PyData meetup](http://www.slideshare.net/textkernel/practical-deep-learning-for-nlp) with a `keras` demo. 
Given the experimental nature of my enterprise I started out directly in a Jupyter notebook running locally on my Mac. However, after building more and more layers with more and more filters and starting to tune the hyperparameters for my networks, I noticed that the training time is starting to slow me down. Hence, it was time to move to an AWS EC2 machine with a dedicated GPU to speed up my experiments. In the following I will describe the steps I took to get to the point of training a NN with `keras` in a Jupyter notebook running on an EC2 instance. 

### 1. Launch an EC2 Instance With a Suitable AMI

Choosing the right AMI (Amazon Machine Image) will save us a lot of installation time once the machine is launched. Since our goal is to do some deep learning, I suggest looking for an AMI that comes with the deep learning library of your desire. In my case I wanted to use either `tensorflow` or `keras` with a `tensorflow` backend. Some searching in the AWS Marketplace reveals that [Amazon's Deep Learning AMI](https://aws.amazon.com/marketplace/pp/B01M0AXXQB) and [Bitfusion Ubuntu 14 TensorFlow AMI](https://aws.amazon.com/marketplace/pp/B01EYKBEQ0) are nice options. In the end I opted for the Amazon AMI and installed `keras` myself with the preinstalled `anaconda` (see next step). `jupyter` is also already preinstalled on both. 

After choosing the AMI we also need to choose the right instance type. Reasonable choices are the g2 and p2 instances, both of which have dedicated GPUs. I opted for a p2 machine, since they are [newer](https://aws.amazon.com/blogs/aws/new-p2-instance-type-for-amazon-ec2-up-to-16-gpus/) and basically [designed for the best deep learning performance](http://www.bitfusion.io/2016/11/03/quick-comparison-of-tensorflow-gpu-performance-on-aws-p2-and-g2-instances/).

I leave all other launch options to their default values, apart from the security group options. Here we need to make some changes as we want to be able to access the Jupyter server from our browser later on.

| Type		| Protocol	| Port Range	| Source |
|-----------|-----------|---------------|--------|
| HTTPS		| TCP		| 443			|0.0.0.0/0	|
| SSH		| TCP		| 22			|0.0.0.0/0	|
| Custom TCP Rule	|TCP	|8888		|0.0.0.0/0	|


### 2. Set up the Environment on the Remote Machine

If the chosen AMI contains all the libraries you need you can skip this step. In my case I had to install `keras` myself, which was quite easy with to do with the preinstalled `conda` tool. 

    ssh ec2-user@ec2-xx-xxx-xx-xxx.eu-west-1.compute.amazonaws.com


### 3. Configure the Jupyter Server


### 4. Run the Jupyter Server


### 5. Have Fun Experimenting with NNs

