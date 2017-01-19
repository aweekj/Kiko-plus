---
layout: post
title: "한글 문서 스타일 샘플"
description: "한글로 된 글의 샘플입니다."
date: 2017-01-19
tags: [샘플 포스트, 테스트, 스타일]
comments: true
share: true
---

이 글은 스타일을 지정하는 데 필요한 모든 것입니다. 단락 내의 많은 임베디드 요소를 보려면 소스 코드를 확인하세요.

--- 

## 1. 제목

# 제목 1

## 제목 2

### 제목 3

#### 제목 4

##### 제목 5

###### 제목 6

### 1-1. 제목 정렬

##### 왼쪽(기본)

##### 가운데
{: .center}

##### 오른쪽
{: .right}

## 2. 본문 

Lorem ipsum dolor sit amet, [test link](#) adipiscing elit. **This is strong.** Nullam dignissim convallis est. Quisque aliquam. *This is emphasized.* Donec faucibus. Nunc iaculis suscipit dui. 5<sup>3</sup> = 125. Water is H<sub>2</sub>O. Nam sit amet sem. Aliquam libero nisi, imperdiet at, tincidunt nec, gravida vehicula, nisl. <u>Underline</u>. Maecenas ornare tortor. Donec sed tellus eget `COPY filename` sapien fringilla nonummy. Mauris a ante. Suspendisse quam sem, consequat at, <del>Dinner’s at 5:00.</del> commodo vitae, feugiat in, nunc. Morbi imperdiet augue <mark>mark element</mark> quis tellus.

## 3. 이미지

![큰 이미지](http://placehold.it/800x400)
![중간 이미지](http://placehold.it/400x200)
![작은 이미지](http://placehold.it/200x200)

### 3-1. 이미지 가운데 정렬
![이미지 가운데 정렬](http://placehold.it/200x200){: .center-image}

## 4. 인용구

> Lorem ipsum dolor sit amet, test link adipiscing elit. Nullam dignissim convallis est. Quisque aliquam.

## 5. 리스트

### 순서가 없는 리스트

* Lorem ipsum dolor sit amet, consectetur adipiscing elit.
* Nam ultrices nunc in nisi pellentesque ultricies. Cras scelerisque ipsum in ante laoreet viverra. Pellentesque eget quam et augue molestie tincidunt ac ut ex. Sed quis velit vulputate, rutrum nisl sit amet, molestie neque. Vivamus sed augue at turpis suscipit fringilla.
* Integer pretium nisl vitae justo aliquam, at varius nisi blandit.
  1. Nunc vehicula nulla ac odio gravida vestibulum sed nec mauris.
  2. Duis at diam eget arcu dapibus consequat.
* Etiam vel elit in purus iaculis pretium.

### 순서가 있는 리스트

1. Quisque ullamcorper leo non ex pretium, in fermentum libero imperdiet.
2. Donec eu nulla euismod, rhoncus ipsum nec, faucibus elit.
3. Nam blandit purus gravida, accumsan sem in, lacinia orci.
  * Duis congue dui nec nisi posuere, at luctus velit semper.
  * Suspendisse in lorem id lacus elementum pretium nec vel nibh.
4. Aliquam eget ipsum laoreet, maximus risus vitae, iaculis leo.

### 정의 리스트

kramdown
: A Markdown-superset converter

Maruku
: Another Markdown-superset converter

## 6. 표

| 상단1 | 상단2 | 상단3 |
|:-----|:----:|-----:|
| 셀1  | 셀2  | 셀3  |
| 셀4  | 셀5  | 셀6  |
|----
| 셀1  | 셀2  | 셀3  |
| 셀4  | 셀5  | 셀6  |
|=====
| 하단1   | 하단2 | 하단3 |


## 7. 코드 스타일

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
