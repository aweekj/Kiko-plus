---
layout: post
title: Classes and Instances!
---

Hello everyone and welcome to my newest technical blog post - this week we are going to talk about the importance of having classes in Ruby...but before we get into why they are so important, what the hell is class?  Well, classes are pretty much blueprints that are used to construct objects.  When we want to create a new object, we use a specific class to create that object, and these objects can mirror many things we see in the real world.  For example, we could have a class called MetroCard that we use to create new instances of a Metrocard. All we need to do to define a class is use the keyword class, and then specify the name of our new class, like below:

```
class MetroCard
end
```

Between the class name and the <code>end</code> keyword, we can write different methods for this class.  Methods are essentially messages that this class uses to communicate with itself and other objects.  The first method always needed in a class is <code>initialize</code> which is run everytime we create a new instance of a class.

    class MetroCard
      def initalize(amount)
        @amount = amount
        puts "Here is your new Metrocard, you have a balance of $#{@amount}"
      end
    end

When we create a new instance of class, we are creating a new object and telling it to inherit all of the methods and traits from that class...and each instance is an entirely separate object...so two MetroCard objects that are created from the MetroCard class will have identical methods, but are two separate objects.  Since our initialize takes one argument, <code>amount</code>, we must pass the amount we want to put on the Metrocard anytime we create a new one.  So, in order to create a new instance of a Metrocard with $10.00 on it, we would call the following:

    new_card = MetroCard.new(10)


Creating a new instance of Metrocard will run the initalize method, assign the amount to our instance variable, <code>@amount</code> and then print out a string informing us of how much we have on this newly created card. But wait, <strong>what is an instance variable?</strong>  Instance variables are things that an object knows about itself and are variable names, but with an "@" at the beginning of the name.  Instance variables are used as references within a class so other methods can take this information, look at it, manipulate it and output it to user.

So, for our next method in our MetroCard class, we need to create a way to "Swipe" our card and spend the money we have on it...and this will illustrate why we use instance variables.  Swiping our card is just another way of sending a message - so in order to do that, we create a method:

    def swipe
      puts "SWIPE" # prints swipe to screen, letting user know its been swiped
      @amount -= 2.50 # subtract the amount of one metro ride from the existing amount
      puts "You now have $#{@amount} left on your MetroCard" # outputs remaining balance
    end

So this method, <code>swipe</code>, mutates the value of our instance variable <code>@amount</code>.  Becaues this is an instance variable, it is available to all methods in the MetroCard class and keeps track of itself as it is mutated by various methods.  Similar to the <code>swipe</code> method, we can create another <bold>instance method</bold> called <code>refill</code> so we can put more money on our existing Metrocard instead of buying a new one.

    def refill(refill_amount) # accepts one argument of how much to add to card
      @amount += refill_amount # adds the refill_amount to the @amount
      puts "You now have $#{@amount} on your MetroCard" # outputs new balance after refilling
    end

So, once again we are changing the instance variable <code>@amount</code> by using the method <code>refill</code> that accepts one argument of how much to add to the card.  With this amount, the method then adds it to the existing balance, aka our instance variable <code>@amount</code>.  Check out a more complete version of our MetroCard class below and how all of the methods can be called on our newly created instance of MetroCard named, x.

<script src="https://gist.github.com/johnlyden/d613f44f16ac6c8d34db.js"></script>

So, you can see how important classes are when it comes to object oriented programming, because that is how we create new objects and make them able to communicate with each other.  Everything is defined in the class of that object.  Stay tuned for more.  Peace out.