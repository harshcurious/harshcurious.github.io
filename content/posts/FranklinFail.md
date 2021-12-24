---
title: "FranklinFail"
date: 2021-02-27T17:56:37+05:30

tags: ["franklin", "website", "julia", "coding", "windows 10", "fail"]
author: "Me"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "Trying to make Frankin work on Windows 10"
#disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
searchHidden: false
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
---

# My Failed Attempt at Setting Up This Website Using Franklin (On Windows)


 I will be using [Franklin](https://franklinjl.org/) based on Julia because
 1. I wanted to learn Julia
 2. I wanted to use markdown (or somethng similar) with LaTeX support automatically
 3. I wanted to see if the promises of KaTeX rendering hold water
 4. Code highlighting was another bonus


## Installing Julia on Windows 10

To do this I first installed Julia using Chocolatey with the command

> choco install julia --confirm

In reality I first used the official Julia insaller, but by default it installs Julia in a folder with the version number. [This makes it really hard](https://discourse.julialang.org/t/what-is-the-best-way-to-set-the-path-to-julia-on-windows-10/16467/12 "Discorse question about setting PATH for julia") to add it to your PATH in the Powershell. Chocolatey on the other hand, handles it all for you and you can start using Julia by typing `julia` on the Powershell prompt. Also, updating Julia will be way easier, just run the command `choco upgrade julia --confirm`.

## Setting Up Atom to use as my markdown editor

I have borrowed a lot of what I am sharing from these two wonderful resources [1](https://www.portent.com/blog/copywriting/content-strategy/atom-markdown.htm "How to Set Up & Use Atom as a Markdown Editor
") and [2](https://github.com/benmarwick/atom-for-scholarly-writing-with-markdown).

Install (using the installer at [Atom.io](https://www.atom.io/)) and open Atom. Close all the welcome messages (after reading them if you feel like it). Click **File >> Settings**. Now go to the install option and search and install the following packages

* _markdown-writer_ : improves the markdown editing process especially for static blogs
* _markdown-preview-plus_ : provides real-time preview of markdown with LaTeX support
* _language-markdown_ : Adds grammar support for Markdown, and smart context-aware behavior to lists
* _autosave_ : protects your work by saving it periodically
* _highlightselected_ : highlights occurance of the selected word
* _linter-retextjs_ : gives feedback on your writing
* _pandoc-convert_ : if you want to directly convert your markdown file into HTML
* _auto-terminal-powershell_ : open powershell terminal in the current file's directory
* _wordcount_ : if you want to see the wordcount of your document

If you have never written in markdown before, [this](https://franklinjl.org/syntax/markdown/ "Basic Guide") is an excellent resourse. I am using [this markdownguide page](https://www.markdownguide.org/basic-syntax/#unordered-lists) as my **reference** for markdown syntax.

## Installing Franklin

First type `julia` in the powershell to get to the Julia prompt `julia>`. Them press `]` to get to **pkg**, julia's package manager. You prompt will change to `(@v1.5) pkg>`. Now type
```julia
add Franklin
```
and Franklin package will be installed. Once this package is intalled, (optionally) install the NodeJS package
```julia
add NodeJS
```
Now the nest commands on the official website are clearly for linux
```julia
using NodeJS
run(`sudo $(npm_cmd()) install highlight.js`)
```
I wasn't able to modify it to get it to work for me. This is the point where I gave up.
My Node.js is in `D` directory whereas the julia directory is `C`. I will have to edit the [NodeJS.jl file](https://github.com/davidanthoff/NodeJS.jl/blob/master/src/NodeJS.jl) to make this work. I don't wanna do that right now. Maybe someday I will get back to it. I did set up atom to use markdown which is great.
