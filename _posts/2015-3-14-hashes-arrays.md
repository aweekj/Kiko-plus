---
layout: post
title: Hashes and Arrays!
---

Welcome to my third technical blog, coming to you LIVE from the end of week three at Dev Bootcamp.  This has been a very good week - much better than the last which was full of frustration and cuss words.  This week we dove right into learning about Ruby - we learned about strings, writing methods, and how to make a program “think.”  During this week we also learned about a few very powerful classes: arrays and hashes.


Arrays and hashes are both used to store collections of information and are common concepts within computer programming in general, not just Ruby.  While both classes are used to contain information, they are different in terms of their uses and methods they accept.  I want this blog post to be crystal clear so I’m going to try and make this as simple as possible.  I’ll just break it down one at a time…lets start off with arrays.

<h2 class="heading">Arrays</h2>

Arrays look like this:
<xmp>names = [“John”, “Jane”, “Josh”, “VLAD THE IMPALER”]</xmp>


This array, names, is just a collection of…ummm….names.  Each element in this array is a name and is integer-indexed in the array - this means that each name has a unique position within the array.  Its as if this array is a collection of real people and everyone in this array is standing in line.  We can talk to each person in this collection by calling them with their unique position in the array.


The crazy thing about arrays is that the first index numbered position starts with 0, not 1.  So, in our example John is in position 0, Josh is in position 1, Alex is in position 2, and VLAD THE IMPALER is chilling in position 3…even though he’s the fourth person in line.


So, in order to access a specific name, we use the following syntax:
<xmp>
names[0] # calls John
names[1] # calls Josh
</xmp>
also, you can use negative position numbers to start from the end and work your way back:
<xmp>names[-1] # calls VLAD THE IMPALER</xmp>

<h2 class="heading">Hash</h2>

No…not that hash.  Similar to the array, a hash is also a collection of information, but this collection is not indexed with integer positions, in fact, there is no order to a hash.  Instead, the information within a hash is indexed through arbitrary keys of any object type, and each key is associated with its own value.  Hmmmmm...looking at that last sentence, I’m not sure that's clear enough…let me show you what a hash looks like:
<xmp>
age = { “John” => 28,
“Jane” => 27,
“Josh” => 30,
“VLAD THE IMPALER” => 585
}
</xmp>


When the hash is created, we input the key on the left and the <code>=></code> operator will connect that key with the value you set it to on the right.


So, in the example above, each element is made up of a name, which is the key, and an age, which is the value.  Each name is associated with its own age, and that is how the information is indexed.  If we wanted to reference VLAD THE IMPALER’s age, we would do so like this:
<xmp>
age[“VLAD THE IMPALER] # this would yield his age, 585
</xmp>


Another typical use of a hash is to store complete strings along with their abbreviations.  Its ideal for a collection of information that has no specific order, and can be referenced with a key and value. So, in conclusion, both arrays and hashes are collections of information, they just differ from each other in how the information is indexed. I hope you learned something today, I KNOW I DID! peace out.
