---
title: "How to Iterate in Python"
date: 2021-03-04T10:48:28+05:30
draft: false

# weight: 1
# aliases: ["/first"]
tags: ["python", "py4e", "learning"]
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
## The `while` loop
It allows you to repeat a set of actions until a statement is true. Eg:
```Python
n = 5
while n > 0:
    print(n)
    n = n - 1
print('Blastoff!')
```
This is executed as follows
+ Creates and sets n to 5.
+ Goes to the `while` statement and checks if n is greater than 0. Right now it's true, so we move inside the loop.
  - Prints n, ie outputs 5.
  - Reduces n by 1, ie n is now 4
+ Goes back to the while statement
  - Checks if n is still greater than 0. It is, so we again move inside the `while` loop.
  - Prints 4.
  - Reduces n by 1.
+ Goes back to the while statement
  - ...
  - ...
+ This goes on until n = 0. When this happens, we exit the `while` loop and go to the statement after that which is `print('Blastoff')`. So the probram outputs `Blastoff` and ends.

## Infinite loops

Don't write infinite loops. Eg:
```
Lather, rinse, repeat
```
or
```python
n = 10
while n < 20:
    print(n, end=' ')
    n = n - 1
print('Done!')
```
### `break` statement
We still sometimes use infinite loops with the `break` statement for more complicated testing conditions. A simpler example is
```python
while True:
    line = input('> ')
    if line == 'done':
        break
    print(line)
print('Done!')

# Code: http://www.py4e.com/code3/copytildone1.py
```
Here the loop runs repeatedly until it hits the break statement when the user inputs `done`.

### `continue` statement
This one ends the current iteration and makes it move onto the next iteration of the loop. The loop still goes on. Eg:
```python
while True:
    line = input('> ')
    if line[0] == '#':
        continue
    if line == 'done':
        break
    print(line)
print('Done!')

# Code: http://www.py4e.com/code3/copytildone2.py
```
An iteration ends if the the first letter of the input is `#`. A sample output is :

![copytildone2](/static/py4e/chapter5/coptildone.png#center)


## The `for` Loop
