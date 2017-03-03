---
layout: post
title: Class Methods!
---

Put on your thinking caps because this is another technical blog post coming to you live from a gloomy Sunday afternoon.  Today, I'm going to talk about class  methods, something I have become very familiar with during this last week of Unit 2.  You might be asking yourself, instance methods...class methods...whats the difference?

An instance method is a method that belongs to in instance that is created from a class.  So, if we have a class known as <code>class Human</code> and we create a new instance of the class human with the class method <code>.new</code>, then that object we created will have instance methods, or methods that are stored in the class which the object inherits. Check out the example below where we define a class, define an instance method, create a new object from that class, and then call that instance method on that object

{% highlight ruby %}
class Person
  def greet # instance method
    puts "hello"
  end
end

john = Person.new
john.greet # outputs "hello"
{% endhighlight %}


So, now that we know what an instance method is, what's a class method?  In order write a class method, we must first go over the concept of Self.  Self is a context sensitive keyword - it is referring to the object that is calling.  For example if you are in the <code>class User</code> and you call <code>puts self.inspect</code> it is gong to return "User" because self is the class that we are currently in.  So, if we want to designate a method specifically for a class, we have to define it in that class and preface the name of the method with self, because the context of self here is the class.  See below for an example of defining a class method and then calling that class method

{% highlight ruby %}
class Person
  def self.hello
    puts "Yooo"
  end

  def greet # instance method
    puts "hello"
  end
end

john = Person.new
john.greet # outputs "hello"
Person.hello # outputs "Yooo"
{% endhighlight %}
So when do you use a class method?  You use them for things that do not deal with an individual instance of a class.  You use them when you want to call a method on the class overall, and not each individual object created from that class.  They are a bit more complicated and less common than instance methods.  Well anyways, thanks for reading, happy coding!  Peace out!