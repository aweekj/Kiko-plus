---
layout: post
title: React.js Project - seems cool
---

Ever since I finished DBC and had time to actually figure out what technologies I want to learn independently, I have battled a few different monsters..mostly within the realm of front-end frameworks.  Obviously I wanted to learn one really well so I can have that holstered in my toolbelt, but there are so many damn options...I know that they all have benefits over the each other and different situations will favor different frameworks, but I want to have one down HARD so I can use it for all kinds of stuff WHENEVER I WANT!

The [NightShift]({% post_url 2015-09-15-nightshift-1 %}) program has opened my eyes to a framework that I hadn't really thought about too much, and that is [React](https://facebook.github.io/react/).  I'm not sure why they prefer this framework for our group projects, but they have been sending React tutorials and are wanting to see React in our stack...so I just been learning some React and guess what, I LIKE IT SO FAR!

Today I finished my first React project that works on top of a Rails API.  This was a perfect starter project to get ready for the United Way application because we are going to need a database of information to interact with.  Most likely, the project will end up being a similar stack, Rails API with React Frontend.

[![expense-tracker](/images/expense-tracker.png)](https://obscure-fortress-4475.herokuapp.com/)

In my brief interactions with React, I can gather that there is not a huge learning curve - it implements core Javascript concepts such as event handlers and bindings, which make it easier to learn...simplicity is one of its major strengths.  As with a lot of frameworks, there are a lot of things happening automagically, but I feel like I get it.

Rather than having multiple states like other frameworks, React has components that can describe the view of your application at any point in time.  Components are essentially reusable APIs that have a render function which draws your markup onto the DOM - it returns a representation of your view.  Rather than a two-way data binding idea like other frameworks utilize (changing the data, changes the model and the model then changes the view), everytime something changes with React the view is blown away and it is re-rendered...but it is done very efficiently.

To do this we don't worry about going from state A to state B, it is always state 0 to render.  When a page is loaded, a component is initially rendered.  When any data changes, React builds a new virtual DOM and then compares the differences between the new virtual DOM and old DOM.  It then finds the differences between the two and finds the minimal set of DOM mutations to perform in order to affect only what has changed.  React pushes the complexity of DOM mutations into the framework, so there is  a log of magic...but I understand that through this magic it is highly effective.

Anyways, check out the [expense tracker](https://obscure-fortress-4475.herokuapp.com/) and then checkout [the code](https://github.com/johnlyden/accounts).  Feel free to let me know if this blog post made sense and if it sounds like I'm understanding this shit.