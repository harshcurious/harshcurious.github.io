---
title: "Kolmogorov Arnold Representation Theorem"
date: 2021-03-17T14:59:43+05:30
draft: false

# weight: 1
# aliases: ["/first"]
tags: ["Math", "ML"]
author: "Harsh Kumar"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
hidemeta: false
comments: false
description: "Understanding the Kolmogorov paper."

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

---

The most surprizing aspect of neural networks is their simplicity. I don't mean that the whole of a neural network is simple. It is not. But at any given instant you are either adding numbers or applying a function on one number (a single variable function). Why these two kinds of operations will give you any old function of multiple variables is a mystry to me! Let me take a small step towards understanding this by reading [this really old paper by Kolmogrov](https://mathscinet.ams.org/mathscinet-getitem?mr=111809 "mathscinet link"). This paper is in Russian, I found an English translation [here](https://cs.uwaterloo.ca/~y328yu/classics/Kolmogorov57.pdf "This is the best link I found"). For more on the mathematical history of the problem look at the [Wikiedia page on Kolmogorov-Arnold representation theorem](https://en.wikipedia.org/wiki/Kolmogorov%E2%80%93Arnold_representation_theorem) (or superposition theorem). Essentially, this paper is important because it solves the Hilbert's 13th problem for continous functions.



![The weird sets](/static/KolmogorovRepresentationTheoremset.jpg#center)
