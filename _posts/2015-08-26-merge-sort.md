---
layout: post
title: Merge Sort!
---

Captain Obvious here, and I'm here to tell you about how much shit there is to know in computer science.  NOT THAT I DIDN'T KNOW THIS STUFF BEFORE *AHEM*, but there is a lot of stuff I have been brushing up on in preparation for whiteboarding and technical interviews - one such thing that I have come across time and time again is sorting.  Sorting can be extremely important when creating algorithms to solve all of the fudged up problems we shall soon be faced with.

Sorting a data structure is sometimes required in order to find the most efficient solution in terms of time and space complexity.  There are many ways to sort, but not every method is the same or appropriate for every situation.  For small data sets, Bubble Sort, Insertion Sort and Selection Sort might be fine, but they are not really scalable because they have an average time complexity of O(n^2), so the time it takes to complete this sort is directly proportional to the square of the size of the input data set.

Merge sort is great because it has a worst case and average complexity of O(n log n) and a best case complexity of O(n).  This is accomplished by splitting the collection into smaller groups by halving it until the groups only have one element and then merging the groups back together so that their elements are in order.  Check out this [cool animation](http://www.ee.ryerson.ca/~courses/coe428/sorting/mergesort.html) to get a feel of how this thing really works.

The merge sort algorithm comes in two parts - a sort function and a merge function.  In case you were wondering what this might look like in Ruby, look no further than right below this sentence.  warning: this involves [recursion](https://www.youtube.com/watch?v=t4MSwiqfLaY).

{% highlight ruby %}
def merge_sort(m)
  return m if m.length <= 1

  middle = m.length / 2
  left = merge_sort(m[0...middle])
  right = merge_sort(m[middle..-1])
  merge(left, right)
end

def merge(left, right)
  result = []
  until left.empty? || right.empty?
    result << (left.first<=right.first ? left.shift : right.shift)
  end
  result + left + right
end
{% endhighlight %}

So we keep halving the array until each half consists of 1 or less elements, we then unwind and compare the first element of the left with the first element of the right, shifting the array containing the lesser value element which pushes that element into our result array.  So, if you need to create an algorithm that, without being sorted, is facing a time complexity of O(n^2) you can probably do better by first sorting.  Sorting the array only costs you O(log n) and then adding a single iteration over that sorted array results in an extra O(n), bringing you to a total time of O(n log n) which is a vast improvement over the original speed of O(n^2).
