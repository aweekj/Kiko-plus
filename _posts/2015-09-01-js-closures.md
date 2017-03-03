---
layout: post
title: Closures!
---

Happy September everyone - today marks a new day in the year of my dog, Lord Butters.  Today I would like to talk about a concept that seems to be a pretty common topic in technical interviews in regards to Javascript...that's right, I'm talking about closures.

My girlfriend has been helping me with specific technical interview questions lately.  last night while my dog, Lord Butters, looked on in confusion as we were jogging in place on an endless running machine, she asked me to describe what a closure is and when is appropriate to use one.  In between my heavy breathing as I was running at level 5.5 at an incline of 3 (impressive, I know), I blurted out, "A closure is a function that is defined inside of another function - one function returns the value of another function that is enclosed inside of it.  Closures have access to the outer function's variables and is a way to sort of create a private method in Javascript."  She said, "ok?"  It was then that I realized, I need to be able to explain this shit a little better.  Here is an attempt to do so:

Closures are functions that refer to the environment in which it was created.  So, since it is a function, inside of another function, and each function defines a new environment scope, the inner function has access to its own scope, the outer function's scope and the global scope...yet the global scope does not have access to the inside of either function, since they both define new scopes...does that make sense?  Its like, each function can look outwards to the next function all the way to the global scope, but that inner function cannot be called from outside of it's enclosing function (globally).

One such application of a closure is to declare private methods, meaning they can only be called by other methods in the same class. This idea parallels a lot of object oriented principles, such as data hiding and encapsulation.  Creating private methods through enclosures restrict access to code and also provide a way to manage the global namespace.

Defining public functions that can access private functions and variables, using closures is also known as using the module pattern, which is another concept hiring dudes want to hear about.  Check out this code example from [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures), an excellent resource for Javascript.

{% highlight javascript %}
var counter = (function() {
  var privateCounter = 0;
  function changeBy(val) {
    privateCounter += val;
  }
  return {
    increment: function() {
      changeBy(1);
    },
    decrement: function() {
      changeBy(-1);
    },
    value: function() {
      return privateCounter;
    }
  };
})();

console.log(counter.value()); // logs 0
counter.increment();
counter.increment();
console.log(counter.value()); // logs 2
counter.decrement();
console.log(counter.value()); // logs 1
{% endhighlight %}


So, In this example, a single environment that was created through the <code>ChangeBy</code> function, is shared by three functions which must be called in relation to their namespace, or outer function <code>counter</code>.  In other words, calling <code>increment()</code> will not work because we do not have access on the global scope - we must call it on the outer function that defines that environment <code>counter.increment()</code>.

Similarly, the shared environment created in the body of the first anonymous function allows access to the privateCounter variable, but only from inside of that private environment that is encapsulated from the global scope, keeping this truly private.

I hope that makes sense.  [Hit me up](http://www.twitter.com/dirtsquad) if you would like more detail