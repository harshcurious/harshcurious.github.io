---
title: "Today I Learnt 4"
date: 2021-04-05T09:37:47+05:30
draft: false

# weight: 1
# aliases: ["/first"]
tags: ["TIL", "notes"]
author: "Harsh Kumar"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
hidemeta: false
comments: false
description: "Notes on what I learnt on April 05, 2021."

disableShare: false
# to disable highlightjs
disableHLJS: false
searchHidden: false
# cover:
#   image: "<image path/url>" # image path/url
#   alt: "<alt text>" # alt text
#   caption: "<text>" # display caption under cover
#   relative: false # when using page bundles set this to true
#   hidden: true # only hide on current single page

plotly: false #turn plotly support on and off
mathjax: false #turn mathjax support on and off
---

## Industry TV series

Just brilliant. The complexities of all the relationships and actions is well thought out. The decisions made were well suited to the characters. It was all around just a well made show. I am impressed. Would recommend to all most anyone. The only point against it is that it has a very cynical worldview

## My notes from [The Basics of CSS: Selectors](https://youtu.be/yh3W6qMxIiA)

Websites are composed of

1. HTML : A markup language. [^1]
2. CSS : What this video is all about.
3. Javascript : Logic that your browser can execute.

[^1]: What's up with mark*up* and mark*down*. Is it like a bottom-up vs top-down approach to text?

To use css just pick a block element in the HTML (the selector) and put certain styling information under it (the properties). Eg:

```css
ul {
  margin: 0;
  padding: 0;
}
```

Here `ul` is a selector which target the _unordered list_ elements. In this particular case it changes the margin, and padding amount.

You can also target an HTML tag by the parent tag around it , i.e. **compound selectors**. For example to target an unordered list inside the nav tags, you can do the following:

```css
nav ul {
  margin: 0;
  padding: 0;
}
```

In this case the `nav` tag does not need to be the immediate parent. There can be other tags/layers between them.

You query for a _class_ with a dot. Eg:

```css
.article-title {
  font-size: 2rem;
}
```

You can combine these two. Eg:

```css
article.content{
    font-size: 2rem;
```

This looks for a _class_ `content` inside an `article` _tag_. A given tag can have multiple classes. These classes are delineated by a space. Eg: `<h1 id="css-selector" class="content body-head"> Pick a Heading </h1>`

You use a `#` to target an id. Eg, to target the prior `<h1>` tag we can write the following:

```css
#css-selector {
  width: 150%;
}
```

An _id selector_ has higher priority to a class selector. It is more specific. Similarly `h1.content` is more specific than `.content`. This can be very tricky in CSS. Classes are more specific than just tags. For the same tag, the css mentioned at the bottom has higher priority than the one above it.

## Learning to Type

I have decided to finally start learning how to type quickly using the 10 finger method. Why learn to type ? My current method of pecking is quick for short burst but not for proper note taking. My aim is to be able to type LaTeX notes live. Also, time is inversely proportional to typing speed. so we have the following :

| words/min | text input/day | time spent in a year|
|---------- | -------------- | ------------------- |
| 10 | 2 hours | 18 weeks |
| 20 | 1 hour  | 9 weeks |
| 30 | 40 min  | 6 weeks |
| 40 | 30 min  | 4.5 weeks|
| 60 | 20 min  | 3 weeks |

In the long-term this learning time is gonna pay for itself.