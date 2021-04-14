---
title: "Today I Learnt 8"
date: 2021-04-13T13:05:02+05:30
draft: false

# weight: 1
# aliases: ["/first"]
tags: ["first"]
author: "Harsh Kumar"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
hidemeta: false
comments: false
description: "Notes on what I learnt on April 13, 2021."

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

## [Go 101](https://go101.org/article/101.html)

This sets more realistic expectations about Golang. 

### [About Go 101](https://go101.org/article/101-about.html)

Main selling point of Golang:

- Fairly flexible for a static language.
- Unique combination of memory saving, fast program warming-up and fast code execution speed.
- Built-in concurrent programming support.
- Great code readability.
- Great cross-platform support.
- Vibrant group.

I didn't quite understand how this particular book is useful. He says a few things about it, but I did not understand it. I am sold on the style. So let's see how this works out for me.

### [An Introduction of Go](https://go101.org/article/introduction.html)

- There are numerous features of Go listed here.
- Go programmers are often called *gophers*.[^gopher] 

    ![Gopher. From Wikipedia captured by LeonardoWeiss. For details click the image.](https://upload.wikimedia.org/wikipedia/commons/c/cb/Pocket-Gopher_Ano-Nuevo-SP.jpg)

- The most popular Go compiler is `gc`, written in Go. There is a second compiler `gccgo`, but it is no longer a priority for the Go design team. 
- **Go Toolchain** is a set of tools for Go development maintained by Go team. `gc` is a part of this collection.
- The version of Go is consistent with the version of Go Toolchain. There were/are two major versions released each year.
- Go 1.8 made massive improvements in the concurrent garbage collection implementation. Lags caused by garbage collection were massively reduced.
- Go is popular for development in
  - networks
  - system tools
  - databases
  - block chain
- There are signs of usage in
  - game development
  - big data
  - AI
- Drawbacks
  - Go doesn't support arbitrary immutable values. Right now many values which are not supposed to be modified in standard packages are declared as variables. This is a security concern.
  - Go also doesn't support generics for custom types and functions. (I don't understand this one.)

### [The Go Toolchain](https://go101.org/article/go-toolchain.html)

- In order to easily call the `go` command add the `bin` sub-folder to the `PATH` environment variable. 
- Since Go 1.16, project dependencies are managed using *modules*.
- `GOPATH` is an environment variable. The default Go workflow happens entirely inside the `GOPATH`. By default, it's the `go` folder under the home directory of the current user. It has three folders in there.
  1. `bin`: the place where Go program binaries end up.
  2. `pkg`: stores the cached versions of Go modules for local Go projects.
  3. `src`: the place where you *should* store your projects.
-  The simplest Go program:
    ```go
    package main
    
     func main() {
     }
     ```
     - The first line `package main` specifies the package name. 

[^gopher]: Apparently there is an old cartoon called [Go Go Gopher](https://en.wikipedia.org/wiki/Go_Go_Gophers). That's probably where you get the Go mascot. Read about its history on the [Golang blog](https://blog.golang.org/gopher)
  ![The Go mascot!](https://blog.golang.org/gopher/header.jpg)