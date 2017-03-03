---
layout: post
title: Regular Expressions!
---

Regular Expressions let us match specific patterns in a chunk of data.  They are used to find and validate data and are defined between two forward slashes, to differentiate them from other language syntax

{% highlight ruby %}
  “Do you like cats?” =~ /like/
  #this returns the index of the first occurrence
  #of the word it was found or nil otherwise
{% endhighlight %}

if we don’t care about the index we could just use the .include? method

Character Classes - lets you define either a range or a list of characters to match, ex [aeiou] matches any vowel.

{% highlight ruby %}
def contains_vowel(str)
  str=~ /[aeiou]/
end
contains_vowel("test") #retuns 1
contains_vowel("sky") #returns nil
{% endhighlight %}

### the return value when using =~ is either the string index or nil

\w is equivalent to [0-9a-zA-Z_]
\d is the same as [0-9]
\s matches white space(tabs, reg space, newline)

### negative forms

\W anything not in [0-9a-zA-Z_]


'.' matches everything but new lines
### Modifiers

![regex-modifiers](/images/regex-modifiers.png)

