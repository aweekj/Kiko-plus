---
layout: post
title: ADA compliant table
---

Here is an example of an ADA compliant table that I recently built as part of a coding challenge.  This embeded version isn't styled the way I originally designed it because the material design library is messing with the layout of the rest of the site, but you can [click here to see the original](http://john-lyden.com/bank-coding-challenge/index.html) which uses material design.

So what the hell is ADA compliant - Title III of the Americans with Disabilities Act (ADA) requires that businesses and nonprofit services providers make accessibility accommodations to enable the disabled public to access the same services as clients who are not disabled.

In terms of constructing a sortable table such as this, certain elements must be used, including declaring table headers, table rows, and in certain circumstances, table scope and data cell headers to identify if a data cell is associated with more than one column or row.  There are a bunch of guidelines and best practices that coincide with making a webpage or an element easier to be interpreted to users with disabilities...you can peep them all [right here](http://www.w3.org/TR/WCAG20-TECHS/).

{% include boa-table.html %}