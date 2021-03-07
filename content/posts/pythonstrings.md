---
title: "What are Strings in Python"
date: 2021-03-07T15:06:35+05:30
draft: false

# weight: 1
# aliases: ["/first"]
tags: ["python", "strings", "coding"]
author: "Harsh Kumar"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
hidemeta: false
comments: false
description: "My notes from the book Python for Everybody"

disableShare: false
# to disable highlightjs
disableHLJS: false
searchHidden: true
# cover:
#     image: "<image path/url>" # image path/url
#     alt: "<alt text>" # alt text
#     caption: "<text>" # display caption under cover
#     relative: false # when using page bundles set this to true
#     hidden: true # only hide on current single page

---

## It's a Sequence, a Sequence of Characters

- Can access the characters using the braket operator
  ```python
  >>> fruit = 'banana'
  >>> letter = fruit[1]
  >>> print(letter)
  a
  ```
  You get that `fruit[1]` is `a`, the second letter in the string. Remeber counting starts from 0 in Python.
  + the number inside the bracket is called the *index*.
  + Indeces can be negative. But index $\in [-length+1, length -1]$.

- `len` is the built-in function which gives the length of a string.
  ```python
  >>> fruit = 'banana'
  >>> len(fruit)
  6
  ```

- 
