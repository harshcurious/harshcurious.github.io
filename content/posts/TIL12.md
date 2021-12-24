---
title: "Today I Learnt 12"
date: 2021-05-11T13:17:46+05:30
# draft: false

# weight: 1
# aliases: ["/first"]
tags: ["TIL", "notes","Kolin"]
author: "Harsh Kumar"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
hidemeta: false
comments: false
description: "Notes on what I learnt on May 11, 2021."

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

## Learning Kotlin

### Creating variables 

Notes from: https://www.programiz.com/kotlin-programming/variable-types and 

- You can define variables dynamically:

  ```kotlin
  var firstname = "Harsh"
  var lastname = "Kumar"
  var age = 26
  var happiness = 0.1
  ```

- You can specify the type:

  ```kotlin
  var firstname:String = "Harsh"
  var age:Int = 43
  ```

- Kotlin variables can be declared in two ways:
  1. `val`: Immutable.
  2. `var`: Mutable.

### Basic variable types 

(<https://kotlinlang.org/docs/basic-types.html>)

- Numerical types: 6 built-in types
    1. `Byte`: values between -128 and 127
    2. `Short`: values between -32768 and 32767 (16-bit signed two's complement integer).
    3. `Int`: values between $-2^{31}$ to $2^{31}-1$ (32-bit signed two's complement integer).
    4. `Long`: values between $-2^{63}$ to $2^{63}-1$ (64-bit signed two's complement integer).
    5. `Float`: (single-precision 32-bit floating point number)
       ![Float Diagram](https://upload.wikimedia.org/wikipedia/en/7/7b/Float_example.PNG)
    6. `Double`: (double-precision 64-bit floating point number)
       ![Double Diagram](https://upload.wikimedia.org/wikipedia/commons/thumb/a/a9/IEEE_754_Double_Floating_Point_Format.svg/640px-IEEE_754_Double_Floating_Point_Format.svg.png)
       | Type | Size(bits) | Significant bits | Exponent bits | Decimal digits |
       |------|------------|------------------|---------------|----------------|
       | Float | 32 | 24 | 8 | 6-7 |
       | Double | 64 | 53 | 11 | 15-16 |
  - Operations: 

      ```kotlin
      fun main() {
        println(1 + 2)
        println(2_500_000_000L - 1L)
        println(3.14 * 2.71)
        println(10.0 / 3)
        println(5/3)
        println(11 % 3)
        println(10.0 % 3)
      }
      ```

      Gives the output:

      ```terminal
      3
      2499999999
      8.5094
      3.3333333333333335
      1
      2
      1.0
      ```

    - Conversion: All number types support conversions to other types.
      - `toByte()`: Byte
      - `toShort()`: Short
      - `toInt()`: Int
      - `toLong()`: Long
      - `toFloat()`: Float
      - `toDouble()`: Double
      - `toChar()`: Char
    - Bitwise operations: They operate on the binary level directly with bits of the numbers' representation. They can be applied only to Int and Long.
      - `shl(bits)` : signed shift left
      - `shr(bits)` : signed shift right
      - `ushr(bits)`: unsigned shift right
      - `and(bits)`: bitwise and
      - `or(bits)`: bitwise or
      - `xor(bits)`: bitwise xor
      - `inv()`: bitwise inversion
- `Char`: Characters. Use single quotes around them: `'1'`.
  - Special characters: Start with a backslash:`\t`, `\b`, `\n`, `\r`, `\'`, `\"`, `\\` and `\$`.
  - Unicode characters: Use escape sequence syntax: `'\uFF00'`.
- `Boolean`: objects that can have two values: `true` and `false`.
  - Built-in boolean operations are
    1. `||`: logical OR
    2. `&&`: logical AND
    3. `!`: logical NOT
  - `||` and `&&` work lazily. 
- `String`: string is a sequence of characters in double quotes: `"abcd 123"`.
  - Elements can be accessed via indexing operation: `s[i]`
  - Immutable.
  - Concatenated using the `+` operator: `"abcd" + "xyz"` or `"abc" + 1`.  But remember that in most cases using string templates or raw strings is preferable to string concatenation.
  - *Escaped* string: may contain escaped characters; delimited by double quotes (`"`)

      ```kotlin
      val s = "Hello, world!\n"
      ```

    - *Raw* string: can contain newlines and arbitrary text; delimited by triple quotes (`"""`)

      ```kotlin
      val text = """
        for (c in "foo")
            print(c)
      """
      ```

    - String templates: String literals may contain template expressions - pieces of code that are evaluated and whose results are concatenated into the string. Starts with a dollar sign (`$`) followed by a variable name or an expression in curly braces.

      ```kotlin
      val i = 10
      println("i = $i") // prints "i = 10"
      val s = "abc"
      println("$s.length is ${s.length}") // prints "abc.length is 3"
      ```

- `Arrays`: To create an array, use the function arrayOf() and pass the item values to it: so `arrayOf(1, 2, 3)` creates an array `[1, 2, 3]`. The class has `get` and `set` functions, `size` property, and a few other useful member functions.
  - Count starts from 0 (like Python).
  - Arrays can contain strings:

      ```kotlin
      var ages = arrayOf(15,16,20,35)
      ```

  - You can update a list by simple reassignment:

      ```kotlin
      ages[2] = 18
      ```

  - `ArrayList`: Dynamic arrays. Can create an array without any elements.

      ```kotlin
      var name = ArrayList<String>()

      name.add("Harshita")
      name.add("Sashi")
      name.add("Camile")
      ```

      You can remove items by:

      ```kotlin
      name.removeAt(1)
      ```

- The basic datatypes don't allow `null` values. To be able to use them, add a question mark (`?`) to the type. (From [this beautiful article](https://typealias.com/start/kotlin-nulls/))

  ```kotlin
  val stars: Int? = null
  val name: String? = null
  ```

  Just remember `Int` and `Int?` are not the same type. Passing them incorrectly to a function might cause errors. 

### Taking Input

- Take input from the user using the `readLine()` command. You get a string out of it. In order to convert it to `Int` use `Integer.valueOf(readLine())`. 

### Control statements

- `if`-`else` is standard:

  ```kotlin
  if(age >18) {
      println("welcome to the app")
  }else {
      println("You are not allowed to use this app")
  }
  ```

- There is a `when` control statement:

  ```kotlin
  var isValid = false    //or true

  when(isValid) {
      false -> {
          println("Please verify your account")
      }
      true -> {
          println("Welcome to the app")
      }
      else -> {
          println("Invalid state")
      }
  }
  ```

### Creating functions

- Define functions using `fun` keyword.

  ```kotlin
  fun printHelloWorld{
      println("Hello world!")
  }
  ```

  - For functions with arguments you have to specify the argument *type*. 

    ```kotlin
    fun printHelloWorldName(name:String) {
        println("Hello world! "+ name)
    }
    ```

  - For functions that return an output, you need to specify the output *type* as well.

    ```kotlin
    fun returnHelloWorldName(name:String):String {
        return "Hello world! " + name
    }
    ```

### Loops

1. `while` loop 

- Bog standard:

    ```
    var count = 0

    while(count < 5) {
        println("Step: " + count)
        count++
    }
    ```

    gives the output:

    ```terminal
    Step: 0
    Step: 1
    Step: 2
    Step: 3
    Step: 4
    ```

2. `for` loop

   standard:

   ```kotlin
   for(count in 0..4) {
        println("Step: " + count)
   }
   ```

    gives the same output as above.

- A function to Loop through an array of strings:

  ```kotlin
  fun showNames(name:Array<String>) {
      for(item in name) {
          println(item)
      }
  }
  ```