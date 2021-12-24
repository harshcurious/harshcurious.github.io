---
title: "Today I Learnt 10"
date: 2021-04-16T15:36:34+05:30
draft: false

# weight: 1
# aliases: ["/first"]
tags: ["TIL","notes","Python"]
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
mathjax: true #turn mathjax support on and off

---

## Lambda Functions in Python

- First I looked at the following article from [realpython.com](https://realpython.com/python-lambda/)

### History

- Lambda calculus (or $\lambda$-calculus) is a formal system in mathematical logic for expressing computation based on function abstraction and application using variable binding and substitution.[^lambdawiki]
- It is a universal model of computation. Alternative to a Turing Machine.
- Until the 1960s, the lambda calculus was only a formalism. Since Richard Montague and other linguists' applied it in understanding the semantics of natural language, the lambda calculus has gained popularity in both linguistics, and computer science.
- Computable functions[^computablewiki] are a fundamental concept within computer science and mathematics. The lambda calculus provides a simple semantics for computation, enabling properties of computation to be studied formally.
- Lambda calculus simplifies the semantics in two ways:
  1. Lambda calculus treats functions “anonymously”, without giving them explicit names.
     For example: 
     > square\_sum$(x,y) = x^2 + y^2$

     can be turned *anonymous* form by rewriting it as 
     > $(x,y) \mapsto x^2 + y^2$

     You now think of it as a mapping of the tuple $x$, and $y$ to $x^2+y^2$.
  2. Lambda calculus only uses functions of a single input. For instance, the square\_sum function is equivalent to the functions 
     > $x \mapsto (y \mapsto x^2+ y^2)$

     This method is known as currying. It transforms a function that takes multiple arguments into a chain of functions each with a single argument.

     We understand this approach to functions by calculating square\_sum at $(5,2)$.
     > $((x,y) \mapsto x^2 + y^2)(5,2)$
     $= 5^2 +2^2$
     $=29$
     
     On the other hand, the curried version requires an additional step.
     > $\left( \left( x \mapsto (y \mapsto x^2 + y^2) \right)(5) \right)(2)$
     $= (y \mapsto 5^2 + y^2)(2)$
     $= 5^2 + 2^2$
     $= 29$

- The lambda calculus consists of a language of lambda terms, which is defined by a certain formal syntax, and a set of transformation rules, which allow manipulation of the lambda terms. 
- **Lambda terms**: The following three rules provide an inductive definition.
  1. A variable, $x$, is itself a valid lambda term.
  2. If $t$ is a lambda term, and $x$ is a variable, then $( \lambda x, t )$ is a lambda term (called an *abstraction*).
  3. If $t$ and $s$ are lambda terms, then $(ts)$ is a lambda term (called an *application*).
  Nothing else is a lambda term. Thus, a lambda term is valid if and only if it can be obtained by repeated application of these three rules.
- I will look at the mathematical background in detail at some other time. Let's move on to Python.

### Understanding Lambda Functions in Python

Let's consider the following simple code:
```python
lambda x: x + 1
```
It can be divided in the following three parts:

![Lambda function structure](/static/TIL/10/LambdaSimple.png)

1. The keyword: `lambda`; indicates that a lambda function is being used.
2. A bound variable: x; refers to the variable to which we are applying the lambda function.
3. A body: x+1; indicates what the lambda function does to the bounded variable.

[^lambdawiki]: [From Wikipedia](https://en.wikipedia.org/wiki/Lambda_calculus).
[^computablewiki]: According to the Church–Turing thesis, computable functions are exactly the functions that can be calculated using a mechanical calculation device given unlimited amounts of time and storage space. Equivalently, this thesis states that a function is computable if and only if it has an algorithm. Note that an algorithm in this sense is a sequence of steps a person with unlimited time and an unlimited supply of pen and paper could follow. [From Wikipedia](https://en.wikipedia.org/wiki/Computable_function).

## Continuing with Go 101

### Introduction to Source Code Elements

https://go101.org/article/basic-code-elements-introduction.html

| command | package |
| ------- | ------- |
| any executable program | importable semantic unit of functionality |

