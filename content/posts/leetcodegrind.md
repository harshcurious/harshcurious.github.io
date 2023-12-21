---
title: "Starting the LeetCode Grind"
date: 2023-12-21T16:31:40+05:30
draft: false

# weight: 1
# aliases: ["/first"]
tags: ["coding", "interview prep"]
author: "Harsh Kumar"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
hidemeta: false
comments: false
description: "Gotta do it for the job search 😿"

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

If you haven't seen my recent Linkedin post, I am looking for a new job as a data scientist. Having been through the interview process in the recent year, there is no template for what might be asked in a data scientist interview. Here are some of the things I have been asked (no particular order):
- Write a Dockerfile from scratch
- Write a full data pipeline in 40 mins; including EDA, feature selection, model selection etc. Thankfully their interview platform crashed by the size of the dataset they asked me to work with!
    - Mind you this was my favorite. At least it's stuff I do on a regular basis. Although the time limit was a bit ridiculous.
- Write 5 SQL queries in 20 mins. This included a median based case statement in MySQL. (Median is not implemented by default in MySQL)
- Obviously LeetCode type python questions. Generally the easy category type.
- Writing the `partial` function for the python library from scratch.
    - Code for reference
    ```py
    def partial(func, /, *args, **keywords):
        def newfunc(*fargs, **fkeywords):
            newkeywords = {**keywords, **fkeywords}
            return func(*args, *fargs, **newkeywords)
        newfunc.func = func
        newfunc.args = args
        newfunc.keywords = keywords
        return newfunc
    ```
- Case study around building a credit card risk assessment model.
- I have been refused to be told what my day-to-day task will include. Likely because my hiring manager had no idea either!
- Obviously the stats related questions: about sampling, information value, Kolmogorv-Smirnoff statistic, A/B testing, z-score, p-values etc.
- The details of various ML and statistical models:
    - Decision trees: how they are built; do they overfit or underfit the data etc.
    - Random forest: uses bagging and feature randomness to create uncorrelated trees
    - xgBoost: boosting; sequential tree creation
    - BERT
    - I haven't given any interviews recently for LLM roles otherwise I will probably encounter prompt engineering

In my experience people are generally looking for certain certain words in these interviews. But most of the ML algorithms have multiple names for the same concept. So you have to be lucky to have the same ideas in mind during the interview.

Given these experiences, I have decided to do everything for my preparations for my interviews, including Leetcode. There is Stratascratch (more data focused), but it is a bit expensive. So I am going to go with Leetcode for now. Stratascratch is something I should look into next year when I want to move to the top companies.

## Today's insights

