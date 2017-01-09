---
layout: post
title: "A Full and Comprehensive Style Test"
description: "Test post for style"
date: 2016-08-15
tags: [test, style]
comments: true
share: true
---

Below is just about everything you'll need to style in the theme. Check the source code to see the many embedded elements within paragraphs.

# Body text

---

# Center Heading 1
{: .center}

# Heading 1

## Heading 2

### Heading 3

#### Heading 4

##### Heading 5

###### Heading 6


Lorem ipsum dolor sit amet, [test link](#) adipiscing elit. **This is strong.** Nullam dignissim convallis est. Quisque aliquam. *This is emphasized.* Donec faucibus. Nunc iaculis suscipit dui. 5<sup>3</sup> = 125. Water is H<sub>2</sub>O. Nam sit amet sem. Aliquam libero nisi, imperdiet at, tincidunt nec, gravida vehicula, nisl. <u>Underline</u>. Maecenas ornare tortor. Donec sed tellus eget `COPY filename` sapien fringilla nonummy. Mauris a ante. Suspendisse quam sem, consequat at, <del>Dinner’s at 5:00.</del> commodo vitae, feugiat in, nunc. Morbi imperdiet augue <mark>mark element</mark> quis tellus.

# Images

![Large example image](http://placehold.it/800x400 "Large example image")
![Medium example image](http://placehold.it/400x200 "Medium example image")
![Small example image](http://placehold.it/200x200 "Small example image")
![Center example image](http://placehold.it/200x200 "Center"){: .center-image}

# Blockquotes

> Lorem ipsum dolor sit amet, test link adipiscing elit. Nullam dignissim convallis est. Quisque aliquam.

# List Types

### Ordered Lists

1. Item one
   1. sub item one
   2. sub item two
   3. sub item three
2. Item two

### Unordered Lists

* Item one
  * sub item one
  * sub item two
  * sub item three
* Item two
* Item three

### Definition Lists

kramdown
: A Markdown-superset converter

Maruku
: Another Markdown-superset converter

# Tables

| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|----
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|=====
| Foot1   | Foot2   | Foot3


# Code Snippets

Syntax highlighting via Rouge

```css
#container {
  float: left;
  margin: 0 -240px 0 0;
  width: 100%;
}
```

Non Pygments code example

    <div id="awesome">
        <p>This is great isn't it?</p>
    </div>
