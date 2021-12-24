---
title: "Let's get Go-ing"
date: 2021-03-08T22:04:51+05:30
draft: false

# weight: 1
# aliases: ["/first"]
tags: ["Intro", "Go", "coding"]
author: "Harsh Kumar"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
hidemeta: false
comments: false
description: "Notes from chapter 1 of the book Go In Action"

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
### Why Go?
- Computer evolution
  - more cores
  - programming languages based on one core programming
- Programming workflow evolution
  - not written by single developer
  - written at different times
  - programmers write library or package to be used elsewhere
  - open source
  - code needs to be shared
- Go
  - rethinks object-oriented development
  - allows for code reuse
  - let's you use all cores
  - no need to recompile evrytime.
- Learn
  - concurrency model
  - fast compiler
  - syntax
  - type system
  - concurrency
  - channels
  - testing, etc

### How Modern programming challenges Go away
- Currently choice between
  - rapid development : Ruby, python
  - fast execution : C, C++.
- Go offers both simultaneously.
- Also, concise syntax : few keywords
- Compiler : less build time.
- Built-in concurrency: no special threading libraries.
- Type system: less overhead; more reusability

#### How is the compiler Go-ing?
- Quick compiles by
  - smart compiling
  - simplified dependency resolution algorithm
  - only looks at the libraries directly used
  - not all dependencies of all libraries included in the dependency chain.

| Dynamic languages | Static languages |
|----|----|
| Types checked on the fly, during execution | Types checked before run-time |
| Less verbose  | Better code completion  |
| Easier to make change; no wait for recompilation  | Allows compiler optimization  |
| Less  | More searchable |
| Difficult to work with other type based systems  |  Easier to work with other systems (that rely on ststic type) like relational databases |
| Fewer syntax and semantic errors  | Easier to catch type errors |
| Eg: Perl, Python, JS | C, C++, Java, Go, Rust  |

- Go is a static language
  - compiler catches type differences
  - easier to catch type errors

### Concurrency
- Difficult to be efficient in hardware utilization
- Others need thread synchronization code, prone to errors
- Strongest feature
- Gorutines
  - like threads, use less memory and code
- Channels
  - data structue
  - lets you send typed messages between goroutines
  - syncronization built-in
- Model where you
  - send data between goroutines
  - goroutines don't fight for same data.

#### goroutines
- functions that run simultaneously
- Many goroutines can run on a single thread
- For example, a web server that can handle multiple web requsts.
  - In Go, the net/http library has concurrency built-in using goroutines.
  - In C/Java, need extra code to use threading
- Use less memory than threads.
- Go runtime automatically schedules execution of goroutines

An example of goroutine:
```go
func log(msg string){
    ... some logging code here
}

// Elsewhere in our code after we've discovered an error.
go log("something dire happened")
```

Here the keyword `go` runs the `log` function as a goroutine. You can execute the rest of the program while the logging happened.

- No overhead so there can be thousands of them.

#### Channels
- Data structure that enable safe data communication between goroutines.
- Hardest aspect of concurrency: data isn't unexpectedly modified by concurrently running threads, processes, or goroutines.
- Other languages make it hard to have syncronized changes.
- Channels ensure only one goroutine modifies data at any time.
- Exchange of data between goroutines is synchronized and both goroutines know that the exchange took place.
- Channels don't provide data access protection between goroutines.
  - If copies are exchanged through a channel, then it's fine.
  - If pointers to the data are exchanged, then each goroutine needs to be syncronized if different goroutines are performing read/write actions.

### Type System
<!-- - Heirarchy-free type system.
- Uses **composition** : Just embed types to reuse their functionality
- Not inheritance-based.
- Types are **composed** of smaller types.

#### Simple
- Built-in as well as user-defined types.
- Built-in like `int` and `strings`.
- User-defined types look and operate similarly to C.
- Types can also declare methods that operate on that data.
- Go developers build small types and embed them into lareger types.
- I don't know the syntax of go or Java. I don't understand their explanation about the type system.
- Maybe I will come back later to see what's happening. -->


####There are three layers here:
1. To define a new type, all you need to do is use existing types and add new methods. This is **type composition**.
2. But these new methods, in terms of application, are no different from the inherited methods. This is called **duck typing**. "If it looks like a duck, and it quacks like a duck, it is a duck" (for all intent and purposes). The link that makes it click for me is this [link](https://realpython.com/lessons/duck-typing/). Essentially the idea is you can call `len()` on any Python object that defines a `.__len__()` method. So you don't need to know if the object is `str`, `list`, `dict`, or a userdefined one, (or through inheretence in go).
3. You model behaviour not model type. You don't declare you are implementing an interface. Compiler does the work of checking if your type satify the interface you are using. This the **simple interface** feature in Go.

### ErGo Memory Management
- Has modern garbage collector.
- Don't need to allocate and free memory like C or C++.
- Using this with threading and heavy concurrency is tedious.
- Go does this for you.

## Worst part of the book
Avoids teaching you how to code on your device. How can you tell me to code entirely online. Come on!
