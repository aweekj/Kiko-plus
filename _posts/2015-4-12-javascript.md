---
layout: post
title: JavaScript, What is That?
---

Hello to the millions and millions of people reading this blog each day!  Today we are going to talk about something that was completely new to me: JavaScript!  I didn't even know wtf it was...I didn't know JavaScript wasn't the same thing as Java - I probably sounded like a real newb when I used those two words interchangeably in the past few months.  Anyways, I was a bit intimidated starting a new language after just starting to feel fairly comfortable with Ruby...but it turns out JavaScript hasn't been so bad.  lets talk about something common to both languages, Loops!

I feel like there are more effective ways to loop in Ruby with iteration methods like <code>#each</code>, and <code>#times</code>, but in regards to traditional loops with counters and evaluating the conditions after each loop, I think JavaScript is more effective.  For example, check out the following loop in Ruby that puts out each element of an array.

<script src="https://gist.github.com/johnlyden/172f72543551b5850f7c.js"></script>

As you can see, defining a method to accomplish this task takes 7 lines, and you have to walk through each line to understand why its looping and how long the loop will last.  In JavaScript, you kinda just give the loop all the information necessary for how long to run the loop on just one line.  Check out the function below that accomplishes the same task as the Ruby Method above.

<script src="https://gist.github.com/johnlyden/a02c1101a6a36afbd029.js"></script>

looking at a for loop in JavaScript, the logic behind the loop is all neatly written in one line.  You simply use the keyword <code>for</code> signal the start of a loop.  In the conditions, you have 3 sections separated by semi-colons.  The first part of the loop defines a variable that is like our counter, in this case its <code>i</code>.  It starts at zero.  The second part is the condition that is evaluated during each iteration.  It compares the counter to the length of our array, and as long as it's less than the length of the array, the conditions are true.  After evaluating that the condition is true, the code on the next line is executed.  This code is simply printing the value of the element in position <code>[0]</code> of the array.  After the code below is execued, the last part of the for statement tells what to do with the counter - in this case, the coutner is increased by one through the notation <code>i++</code> and then is evaluated again to see if the conditions are still true.  The conditions will continue to be true on each iteration for the length of the entire array.

Ultimately, I think Ruby kills it in the simplicity department with handy array methods that can have a block of code passed to each element.  Check out the example below that does the same thing as the previous two

<script src="https://gist.github.com/johnlyden/756420e31901d57d5627.js"></script>

That is way shorter, and way cleaner...I like that.  Well lets keep on moving with JavaScript...stay tuned for next week.

Also, check out this game I made in JavaScript.  Its nothing fancy but if you copy the code, and then open the console in your browser (in Chrome just press Command + Option + i) and paste it, you can play.  <a href="https://github.com/johnlyden/phase-0-unit-3/blob/master/week-7/design-basic-game-solo-challenge/my_solution.js"><h3>HERE IS THE LINK.</h3></a>