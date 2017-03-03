---
layout: post
title: Knuth Shuffle!
---

Lately I have been getting ready for the dreaded technical interviews that are destined to be in the near future.  Coming from a business background where everything hinges mostly on behavioral interviews and your past experiences, the technical interview scares me a bit...having to whiteboard out a solution to a difficult problem is tough.

In my preparation for the coming interviews, I have been reading [Cracking the Coding Interview](http://www.amazon.com/Cracking-Coding-Interview-Programming-Questions/dp/098478280X) and practicing some well known interview questions.  One such techincal interview question that I would like to share with you is as follows:

> Given an array of n integers, write a function that shuffles the array in place such that all permutations of the n integers are equally likely

One pointer that I have learned about technical interviews is to think out loud and never freeze up - start small and start to code out something, even if it is a solution that is accomplished through sheer brute force...meaning that it gets the job done even if it isn't efficient in terms of time or space.  Needless to say, my first attempt was not the best answer, but afterwards I learned of a solution that is efficient in both regards.  This solution is a means through whats known as the [Knuth Shuffle](http://rosettacode.org/wiki/Knuth_shuffle#JavaScript), a.k.a the Fisher-Yates shuffle.  Check out the algorithm coded out in Javascript below:

{% highlight javascript %}
function knuthShuffle(arr) {
    var rand, temp, i;

    for (i = arr.length - 1; i > 0; i -= 1) {
        rand = Math.floor((i + 1) * Math.random());//get random between zero and i (inclusive)
        temp = arr[rand];//swap i and the zero-indexed number
        arr[rand] = arr[i];
        arr[i] = temp;
    }
    return arr;
}
{% endhighlight %}

Want to see the same algorithm coded out in Ruby and added as an Array class method??? OK THEN!

{% highlight ruby %}
class Array
  def knuth_shuffle!
    j = length
    i = 0
    while j > 1
      r = i + rand(j)
      self[i], self[r] = self[r], self[i]
      i += 1
      j -= 1
    end
    self
  end
end
{% endhighlight %}

This solution is efficient because it is picking a random number within the bounds of the length of the array as an index of the array, then swapping the element at that given position with an element at position array[i] which is being gradually increased through each iteration as the available random positions is being decremented with each iteration.  The beauty in this solution is that it is acheived in O(n), meaning that it will grow linearly and in direct proportion to the size of the input data set as opposed to my original solution which was O(n^2) and involved nested iterations over the data set.

Happy interviewing everyone!
