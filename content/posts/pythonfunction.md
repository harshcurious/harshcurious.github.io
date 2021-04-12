pythonfunction.md

---
title: "Learning Python: Functions"
date: 2021-03-03T13:25:35+05:30
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
searchHidden: false
# cover:
#     image: "<image path/url>" # image path/url
#     alt: "<alt text>" # alt text
#     caption: "<text>" # display caption under cover
#     relative: false # when using page bundles set this to true
#     hidden: true # only hide on current single page

---
## What is a Function
A **function** takes a set of inputs and produces an output. Eg:
```python
>>>type(32)
<class 'init'>
```
Here `type` is a function that takes `32` as an input and produces its class.

## Some Built-in functions

+ `max` : gives the  “largest character” in the string
  ```Python
  >>>max('Hello world')
  'w'
  ```
+ `min` : gives the  “smallest character” in the string
  ```Python
  >>>min('Hello world')
  ' '
  ```
+ `len` : gives the number of characters in the string
  ```python
  >>>len('Hello world')
  11
  ```
+ Type conversion functions
  - `int` : takes any value and converts it to an integer, if it can, or complains otherwise
    ```python
    >>>int('32')
    32
    >>>int('Hello')
    ValueError: invalid literal for int() with base 10: 'Hello'
    >>>int(3.99999)
    3
    >>> int(-2.3)
    -2
    ```
  - `float` : takes integers and strings, and converts them to floating-point numbers
    ```python
    >>> float(32)
    32.0
    >>> float('3.14159')
    3.14159
    ```
  - `str` : converts its argument to a string
    ```python
    >>> str(32)
    '32'
    >>> str(3.14159)
    '3.14159'
    ```

+ Math Functions
  - Need to import it with the `import math` command.
  - `log_10` : logarithm in base 10
    ```Python
    >>> ratio = signal_power / noise_power
    >>> decibels = 10 * math.log10(ratio)
    ```
  - `pi`
    ```python
    >>> degrees = 45
    >>> radians = degrees / 360.0 * 2 * math.pi
    ```
  - `sin`
    ```python
    >>> math.sin(radians)
    0.7071067811865476
    ```
  - `sqrt`
    ```python
    >>> math.sqrt(2) / 2.0
    0.7071067811865476
    ```

+ Random numbers
  - The `random module` provides functions that generate pseudorandom numbers
    ```python
    import random

    for i in range(10):
      x = random.random()
      print(x)
    ```
    ![pseudorandom image](/static/py4e/chapter4/random.png#center)

  - `randint` : takes two inputs and produces a random integer in the range
    ```python
    >>> random.randint(5,10)
    7
    >>> random.randint(5,10)
    10
    ```
  - `choice` : chooses an element from a sequence at random
    ```python
    >>> t = [1, 2, 3]
    >>> random.choice(t)
    2
    >>> random.choice(t)
    3
    ```

## Defining functions
The *defining* feature of programming languages is their ability to have user defined functions.

In python we define functions in the following way:

![defining function in python](/static/py4e/chapter4/functionpy.png#center)

To call the above function you just type
``` Python
>>> print_lyrics()
I'm a lumberjack, and I'm okay.
I sleep all night and I work all day.
```

If you have defined a function **A** already in your code, you can use it inside a function **B** as long as function **B** comes after function **A** in the *flow of execution*.

To return a result from a function, we use the return statement in our function
```python
def addtwo(a, b):
    added = a + b
    return added

x = addtwo(3, 5)
print(x)

# Code: http://www.py4e.com/code3/addtwo.py
```

void function:    A function that does not return a value.
```Python
>>> print(print_lyrics())
None
>>> print(type(None))
<class 'NoneType'>
```

## Why functions
+  name a group of statements; program easier to read, understand, and debug
+ eliminates repetitive code; changes in one place
+ debug the parts one at a time and then assemble them into a working whole
+ well-designed functions are useful for many programs; write and debug once; reuse it

## Exercise
Solutions
### Exercise 4
```python
inpHours = input('Enter Hours: ')

try:
    hour = float(inpHours)
except:
    print('Error, please enter numeric input')
    exit(0)

inpRate = input('Enter Rate: ')

try:
    rate = float(inpRate)
except:
    print('Error, please enter numeric input')
    exit(0)

def computepay(h, r):
    if h <= 40 :
        pay = r * h
    else:
        pay = (r * 40) + (1.5*r*(h-40))
    print('Pay:', pay)

computepay(hour, rate)
```

### Exercise 5
```python
inp = input('Enter score: ' )
try:
    s = float(inp)
except :
    print('Bad Score')
    quit()

def computegrade(score):
    if score > 1:
        return 'Bad score'
    elif score >= 0.9:
        return 'A'
    elif score >= 0.8:
        return 'B'
    elif score >= 0.7:
        return 'C'
    elif score >= 0.6:
        return 'D'
    elif score >= 0:
        return 'F'
    else:
        return 'Bad score'

grade = computegrade(s)

print(grade)
```
