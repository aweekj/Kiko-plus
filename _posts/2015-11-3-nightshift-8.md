---
layout: post
title: The Nightshift - Week 8
---

##Still Working

Greetings to all - ay imma be straight with u, its gonna be another short post from ya boi today because there's too much to do.  We have two and a half weeks left of Nightshift and its what u would call CRUNCH TIME...because I was crunching on some pizza last night (thin crust OBVIOUSLY).

This week, the week before and all remaining weeks will be mostly centered around just getting work done.  We are still doing talks and having some instruction from the mentors, but its mostly all about getting our features built out.

###Refactoring

The talk last night was all about refactoring, and refactoring is dope once you actually get to that point, lol.  Its hard to think about refactoring when you are still looking at a pretty long list of tasks on the trello board.

But hold up, what exactly is refactoring?  Refactoring is simple:

>Clean Code = Simple Code

More specifically, refactoring is improving your code to be more readable and reusable without changing or adding functionality.  When it comes to refactoring, its best practice to have a nice suite of tests to ensure that nothing breaks throughout the refacotring process...I knew we were forgetting something.

But you don't always have to wait until you have a finished MVP to start refactoring...you can pick up places to refactor as you are writing code.  If you find yourself doing the exact same thing in three different places, chances are you can refactor that into a function and just call that function in those three places.  This is what is known as a CODE SMELL...something that makes your code stink and is an obvious area for refactoring.  Some of the main code smells include:

* Bloaters - Long methods, large classes
* OO Abusers - switch statements,
* Change Preventers - hinders change in the future, divergent change
* Dispensables - Lazy class, dead code, needs to be removed
* Couplers - classes coupled to closely, message chains

I don't want my code to smell so I definitely plan on refactoring before we turn in our final product to the United Way, but right now I gotta get back to building out this feature i'm working on, so peace out i'm going back to my planet.

<blockquote class="instagram-media" data-instgrm-version="5" style=" background:#FFF; border:0; border-radius:3px; box-shadow:0 0 1px 0 rgba(0,0,0,0.5),0 1px 10px 0 rgba(0,0,0,0.15); margin: 1px; max-width:658px; padding:0; width:99.375%; width:-webkit-calc(100% - 2px); width:calc(100% - 2px);"><div style="padding:8px;"> <div style=" background:#F8F8F8; line-height:0; margin-top:40px; padding:50.0% 0; text-align:center; width:100%;"> <div style=" background:url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACwAAAAsCAMAAAApWqozAAAAGFBMVEUiIiI9PT0eHh4gIB4hIBkcHBwcHBwcHBydr+JQAAAACHRSTlMABA4YHyQsM5jtaMwAAADfSURBVDjL7ZVBEgMhCAQBAf//42xcNbpAqakcM0ftUmFAAIBE81IqBJdS3lS6zs3bIpB9WED3YYXFPmHRfT8sgyrCP1x8uEUxLMzNWElFOYCV6mHWWwMzdPEKHlhLw7NWJqkHc4uIZphavDzA2JPzUDsBZziNae2S6owH8xPmX8G7zzgKEOPUoYHvGz1TBCxMkd3kwNVbU0gKHkx+iZILf77IofhrY1nYFnB/lQPb79drWOyJVa/DAvg9B/rLB4cC+Nqgdz/TvBbBnr6GBReqn/nRmDgaQEej7WhonozjF+Y2I/fZou/qAAAAAElFTkSuQmCC); display:block; height:44px; margin:0 auto -44px; position:relative; top:-22px; width:44px;"></div></div><p style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; line-height:17px; margin-bottom:0; margin-top:8px; overflow:hidden; padding:8px 0 7px; text-align:center; text-overflow:ellipsis; white-space:nowrap;"><a href="https://instagram.com/p/9hUvael0KD/" style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; font-style:normal; font-weight:normal; line-height:17px; text-decoration:none;" target="_blank">A video posted by Johnny (@dirtsquad)</a> on <time style=" font-family:Arial,sans-serif; font-size:14px; line-height:17px;" datetime="2015-10-31T23:38:14+00:00">Oct 31, 2015 at 4:38pm PDT</time></p></div></blockquote>
<script async defer src="//platform.instagram.com/en_US/embeds.js"></script>