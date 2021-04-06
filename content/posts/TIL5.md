---
title: "Today I Learnt 5"
date: 2021-04-06T11:17:24+05:30
draft: false
publishDate: 2021-05-06

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
#     image: "<image path/url>" # image path/url
#     alt: "<alt text>" # alt text
#     caption: "<text>" # display caption under cover
#     relative: false # when using page bundles set this to true
#     hidden: true # only hide on current single page

plotly: false #turn plotly support on and off
mathjax: false #turn mathjax support on and off

---
## [Open Source Smart Watch](https://youtu.be/xF_SR6aUKHg)

{{< youtube xF_SR6aUKHg >}}

- Very similar to another project I have already heard about called the [Watchy](https://watchy.sqfmi.com/)
- Made by Paul Smith with news over at [Hackster.io](https://www.hackster.io/news/there-s-something-especially-impressive-about-the-opensmartwatch-project-c2c878b983cf).
- The project has a [website](https://open-smartwatch.github.io/) and a GitHub [organization](https://github.com/Open-Smartwatch).
- It has got a micro-USB port for data transfer and charging.
- The main one has a SD-card slot for data storage. The lite one has no SD-card slot.
- The components used are:
  - EPS32-micro-D4: 2×240 MHz, 320 KB RAM
  - Bluetooth 4.2 BR/EDR BLE
  - Wi-Fi 2.4GHz 802.11 b/g/n
  - GC9A01 240×240 16bit TFT display (round)
  - BMA400 Accelerometer + Pedometer
  - MCP73831 LiPo Charger
  - CH340E USB Serial
  - In the GPS edition
    - Quectel L96 GPS module
    - 4 MB RAM
    - microSD
- This is genuinely fascinating to me. Maybe someday I will make my own.

## Python

```python
list = ["E", "D", "C", "B", "A"]
print(list)
```

This gives you the following:

```python
['E', 'D', 'C', 'B', 'A']
```

Now what if you wanted to print it a different format 🧐. Here are some options from [geeksforgeeks](https://www.geeksforgeeks.org/print-lists-in-python-4-different-ways/):

1. **Using `for` loop**:

   ```python
   for x in list:
     print(x, end=" ")
   ```

   This will give you:

   ```python
   E D C B A
   ```

2. **Without using loops**: `*` symbol is used to print the list elements in a single line with space as the separator.

   ```python
   print(*list)
   # or
   print(*list, sep = ", ")
   ```

   You get:

   ```python
   E D C B A
   # or
   E, D, C, B, A
   ```

3. **Convert the list into a string** : using the `join()` method. [^methodfunction]

   ```python
   print(' '.join(list))
   ```

   Output:

   ```python
   E D C B A
   ```

   - Using `map()` function : we can convert each item in a list to string and then join them.

     ```python
     a = [1, 2, 3, 4, 5]
     print(' '.join(map(str, a)))
     ```

     We get:

     ```python
     1 2 3 4 5
     ```

## Can use tables inside a footnote of Hugo

As long as the table is aligned below the footnote, this works by default (Hugo version 81.0 with Papermod theme).

## Anki

### Python

- Lists are mutable.
- `count()` method returns the number of **non-overlapping** occurrences of substring
- Lists can have multiple occurrences of the same element.
- Slice works in [start:stop:*step*].
- Negative step in slice notation reverses the direction. Eg:
  
  ```python
  t = '12345'
  print(t[::-1])
  print(t[::-2])
  ```

  produces the output:

  ```python
  54321
  531
  ```

- `//` is a floor division operator, division rounded down.
  
  ```python
  >>> a = 5//2
  >>> print a
  2
  ```

### Math

- Simply Connected Domain
- Morera's Theorem
- Cauchy's Integral Theorem
- Winding Number

[^methodfunction]: Found the difference [here](https://www.geeksforgeeks.org/difference-method-function-python/).
  | Method | Function |
  | ------ | -------- |
  | called by its name; associated to an object (dependent)| called by its name (independent) |
  | the object (where invoked) is implicitly passed | parameters (if any) are explicitly passed |
  | may or may not return any data | may or may not return any data|
  | only works in the `class` where it is defined | no `class` involved |
