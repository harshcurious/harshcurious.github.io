---
title: "Today I Learnt 11"
date: 2021-04-18T12:19:03+05:30
draft: false

# weight: 1
# aliases: ["/first"]
tags: ["TIL","notes"]
author: "Harsh Kumar"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
hidemeta: false
comments: false
description: "Notes on what I learnt on April 16, 2021."

disableShare: false
# to disable highlightjs
disableHLJS: false
searchHidden: false
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page

plotly: false #turn plotly support on and off
mathjax: false #turn mathjax support on and off

---
## Python List Operations

If we start with a list 
```python
seq = [1,2,3,4]
``` 
then we have the following operations:

| Python Expression | Results | Descriptions |
| ----------------- | ------- | ------------ |
| `seq + [5,6,7,8]` | [1,2,3,4,5,6,7,8] | Concatenation |
| `seq * 4` | [1,2,3,4,1,2,3,4,1,2,3,4,1,2,3,4] | Repetition |

## Go 101

This is a continuation of my notes on learning Go.

### Keywords

- [From Go 101](https://go101.org/article/keywords-and-identifiers.html)
- Go has precisely 25 keywords:
  ```go
  break     default      func    interface  select
  case      defer        go      map        struct
  chan      else         goto    package    switch
  const     fallthrough  if      range      type
  continue  for          import  return     var
  ```
### Identifiers

- Composed of Unicode letters, Unicode digits and `_` (underscore)
- Starts with a Unicode letter or `_`. (Not a number!)
- Identifier `_` is a special identifier, it is called **blank identifier**.
- All names of types, variables, constants, labels, package names and package import names are identifiers.
  | Exported identifier | Non-exported/unexported identifier |
  | ------------------- | ------------------------ |
  | Starts with upper case letter | Does not start with upper case letter |
  | Kinda like *public* | Kinda like *private* |
  | Shared between files in a package | Local to usually a function or file |
  | Eg: `Player_9`, `DoSomething`, `VERSION`, `Ĝo`, `Π` | `_`, `_status`, `memStat`, `book`, `π`, `一个类型`, `변수` |

- Some items that cannot be used as identifiers:
  | Reason | Examples |
  | ------ | --- |
  | Starting with a Unicode digit: | `1234`, `2clear` |
  | Containing disallowed Unicode character | `a.b`, `*prime`, `$name`, `email@domain.com` |
  | Keywords | `type`, `range` |

## Built-in Types

| Categories | Examples |
| ---------- | -------- |
| Boolean type | `bool` |
| Integer numeric types | `int8`, `uint8`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, `int`, `uint`, and `uintptr`|
| Floating-point numeric type | `float32` and `float64` |
| Complex numeric type | `complex64` and `complex128` |
| string type | `string` |

- There are two built-in type aliases:
  1. `byte`: is an alias of `uin8`.
  2. `rune`: is an alias of `int32`.
- The integer types whose names starting with a `u` are unsigned types.
- The number in the name of a type means how many binary bits a value of the type will occupy in memory at run time.
- The size of `int` and `uint` values are 4 on 32-bit architectures, and 8 on 64-bit architectures.
- The size of `uintptr` value must be large enough to store the uninterpreted bits of any memory address. (I don't understand this statement. How large can a memory address be?)
- The real and imaginary parts of a `complex64` value are both `float32` values, and the real and imaginary parts of a `complex128` value are both `float64` values.
- **Zero value**: Each built-in type has a zero/default value.
  | Category of Type | Zero Value |
  | ---------------- | ---------- |
  | Boolean type | `false` |
  | Numeric types | `0` (might have different size in memory) |
  | String type | Empty string |
  