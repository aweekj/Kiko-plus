---
layout: post
title: An Easier Way to group stuff!
---

Hello and welcome to another edition of John's Technical Blog Posts...a now infamous section of this website that will help you understand some of the concepts we have been learning here at DBC.  Last week we talked about <a href="../blog/t3-arrays-hashes.html">Arrays and Hashes</a> and I think I was a bit long winded and unclear, so this week I'm going to try and demonstrate the concepts a little more clearly with some examples!  So, without further adieu, lets talk about the always exciting enumberable method <code><strong>#group_by</strong></code>

<h2>What is <code><strong>#group_by</strong></code>?</h2>
Just looking at the name of this method, you can tell that it is used to create groups. <code>#group_by</code> is a very useful enumerable method that groups a collection according to the result of a block that is passed to it and returns a hash where the keys are the evaluated result from the block, and the values are the arrays of the elements in the collection corresponding to the key. It looks like this:

    group_by { |obj| block } => a_hash

If that didn't make sense, its ok...I think learning through example is the best way to really understand how any method works.
Lets say you have a collection of numbers, and you want to split this collection into two groups, even and odd numbers.  This is a great situation in which to use <code>#group_by</code>.  We can pass the block <code>{ |x| x % 2 == 0 }</code> which will group all of the even numbers in our collection into an array as the value of one element of a hash, and all of the odd numbers into another:

    array = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16]
    array.group_by { |x| x % 2 == 0 } # checking if each number is divisible by 2
    {false => [1, 3, 5, 7, 9, 11, 13, 15]},
    {true => [2, 4, 6, 8, 10, 12, 14, 16]}

In the example above, we can see that each element of the array was passed through our code block and evaluated if it was perfectly divisible by 2.  This method then grouped the results into a hash with either the key of "true" for the even numbers, or with the key of "false" for the odd numbers.  The values for each key in the hash are returned in the form of an array.

Returning the evaluated collection in the form of a hash is a very useful way to view this information - the key and value pairs aren't in any type of indexed order like the arrays.  Becuase this method is just grouping the information based on the results of the block, it is just presenting the information based on which group each evaluated element fell into.

Moving forward, I can see this being a very popular method that will be used quite often.  Grouping, sorting and manipulating information is a big part of writing programs so its a good thing a helpful method like this already exists!  Thats it for now, Peace out!
