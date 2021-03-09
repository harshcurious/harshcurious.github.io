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
- How to travese through a string:
  1. `while` loop:
      ```python
      index = 0
      while index < len(fruit):
          letter = fruit[index]
          print(letter)
          index = index + 1
      ```

  2. `for` loop:
      ```Python
      for char in fruit:
        print(char)
      ```
- How to slice a string?
  ```python
  >>> s = 'Monty Python'
  >>> print(s[0:5])
  Monty
  >>> print(s[6:12])
  Python
  >>> print(s[:3])
  Mon
  >>> print(s[3:])
  ty Python
  >>> print(s[3:3])
  ''
  >>> print(s[:])
  Monty Python
  ```

- What's **imutable** about 'em'?
  + try this:
    ```python
    >>> greeting = 'Hello, world!'
    >>> greeting[0] = 'J'
    TypeError: 'str' object does not support item assignment
    ```
  + you get an error because strings are *immutable*, ie they can't be changed.
  + instead you need to create a new string:
    ```python
    >>> new_greeting = 'J' + greeting[1:]
    >>> print(new_greeting)
    Jello, world!
    ```

- Fighting for equality:
  - ```python
    if word == 'banana':
      print('All right, bananas.')
    ```
      this checks if the string `word` is exactly the string `banana`.

  - ```python
    if word < 'banana':
      print('Your word,' + word + ', comes before banana.')
    ```
    this checks the **alphabetical order** among strings.

  - All the uppercase letters come before all the lowercase letters
- Are strings Python objects? What's an object?
  - Strings are objects
  - Object contains two things
    - data
    - methods : functions built into objects and available to any instance
  - The `dir` shows avilable methods associated with the object
    ![dir(str)](/static/py4e/chapter6/dirString.png#center)

  - Methods have a different syntax:
    ![methodsyntax](static/py4e/chapter6/methodSyntax.png#center)

  -


## Exercises
My solutions:
1.  ```python
    fruit = 'banana'
    index = len(fruit)
    while index > 0:
        print(fruit[index -1])
        index = index - 1
    ```

    Here in the first statement of the `while` loop I combined two statement and it works.

2.

3. ```python
    def countletter(word, char):
        count = 0
        for letter in word:
            if letter == char:
                count = count + 1
        print(count)

    word = input('Word: ')

    char = input('Letter to count: ')

    countletter(word, char)
   ```

4.
