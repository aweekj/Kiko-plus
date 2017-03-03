---
layout: post
title: Positioning in CSS!
---

CSS and HTML are very powerful when it comes to making a cool looking web page and I think one of the hardest ideas to understand so far, has been positioning.  With this blog post, I am going to attempt to explain the concept of relative, absolute and fixed positioning - something that has been my own personal hell this weekend.

When you create an element in HTML, you can give it a specific ID or Class which you can then use in your stylesheet to give that element specific attributes.  One such property is position, which can have three different settings: relative, absolute and fixed.


The first position we will discuss is fixed position. An element with a position equal to fixed is positioned relative to the browser window.  These elements are removed from the normal flow of things and can overlap other elements.  So, once you declare this element to be fixed, you can then tell it where you want to place it by saying how far from the top and how far from the left you want to place it.  If you can remember back to high school, you can think of this as plotting a point on a graph, with an X and Y value.


The second position we’ll go over is relative.  A relative positioned element is positioned relative to its normal position…what the hell does that mean?  Relative positioned elements are preserved in the normal flow of your document, so when you tell it to move X distance from the left and Y distance from the top, it is positioning the element relative to where it would normally show up in the document.


Absolute positioning is positioned relative to the first parent element that has a position.  This means that if an element is wrapped inside of another element, then you can specify where to position that element in relation to the parent its wrapped in.  It is similar to fixed positioning in that it overlaps and you can specify where to put it, but it is not relative to the browser - it is relative to its parent.


I know this shit is very complicated and hard to wrap your head around with one blog post…I’m still trying to wrap my head around it too TBH.  I hope this was able to shed at least a small amount of light on this complicated concept.  Peace out.
