---
layout: post
title: Ghost Circle in Processing
---

The post from yesterday was a bit misleading, it wasn't as easy as I thought!  I wrote that post and then proceeded to try and publish it for the next hour. Something was going on to where the file was showing up when I previewed on my local server, but would not show up when I pushed to Github.  This website is built in [Jekyll](https://jekyllrb.com/) and hosted with gh-pages...I had found a plugin for jekyll that would make it easier to display my .pde files on Jekyll.  While this worked locally, it wasn't working live so I got frustrated for a while...BUT I DID NOT QUIT!

After some trial and error and getting nothing, I found out that all Github Pages sites are generated using the --safe option which disables custom plugins for security reasons, so of course it wasn't working.  So instead I created html files in my _includes folder and used the liquid templating language to process the template I created, containing my Processing sketch.  (Liquid templating is something I really like about Jekyll).

Anyways, here is another sketch that was created from a [Processing Tutorial](https://processing.org/tutorials/arrays/).  This one is cool because it uses an array to record the previous x and y coordinate of the cursor each time it is moved, storing up to 50 coordinates and displaying these values with an ellipse that creates a trail behind the cursor.  This sketch reminds me of the smoke monster from LOST.

{% include ghost-circle.html %}
