---
layout: post
title:  "Learn Kotlin (Part 1) - Hello world and Basic Data Types"
categories: Programming
tags: Kotlin
---
Post Series: <br />
Part 1: [Hello world and Basic Data Types](https://sudeepacharya.com.np/blog/2018/12/03/learn-kotlin-part-1-hello-world-and-basic-data-types/)<br />
Part 2: [Array, Collection and Range](https://sudeepacharya.com.np/blog/2018/12/10/learn-kotlin-part-2-array-collection-and-range/)<br />
Part 3: [Control Flow](https://sudeepacharya.com.np/blog/2018/12/17/learn-kotlin-part-3-control-flow/)<br />
Part 4: [Function](https://sudeepacharya.com.np/blog/2018/12/25/learn-kotlin-part-4-function/)<br />
Part 5: [Class](https://sudeepacharya.com.np/blog/2019/01/09/learn-kotlin-part-5-class/)<br />


Since [Kotlin](https://kotlinlang.org/) is already a official programming language for Android Apps development, I have been learning Kotlin lately. In this post, i will take you through basic hello world skeleton program to data types, variables in Kotlin.

<h2>Hello World Program for Kotlin</h2>

```kotlin
fun main(args: Array) {
    println("Hello World!")
}
```
main is the entry point in the kotlin program.

<h2>Variables/Values in Kotlin</h2>
We can define either <b>val</b>ue or <b>var</b>aible in kotlin. So, what is the difference between these two declarations?

```kotlin
var a : Int = 3 vs val a : Int = 3
```

When you declare var then you can change the value later whereas if you declare val then you cannot change the value later. val  makes the variable declaration immutable.

<h2>Data Types</h2>
kotlin provides data types like Java, but unlike the java data type starts with capital letter.

<u>Numbers</u><br />
```kotlin
val a : Int = 3;
val b : Float = 3.0f;
val d : Double = 4.9;
val l : Long = 3494949494949
```
Let us see what size of data can each type store.

| Type   	| Size 	|
|--------	|------	|
| Byte   	| 8    	|
| Short  	| 16   	|
| Int    	| 32   	|
| Long   	| 64   	|
| Float  	| 32   	|
| Double 	| 64   	|


<u>Character and String</u><br />
```kotlin
var a : Char = 'd'
val b : Char = 'e'
val name : String = "Sudeep"
```

Char can store one character whereas a String can store group of character.

<u>Boolean</u><br/>
Like other programming languages, kotlin provides boolean data type which can store either true or false.

```kotlin
var isTrue : Boolean = false
var isFalse : Boolean = true
```

These are the basic data types in Kotlin, we have more complex data types such as Arrays, Collection and Ranges which we will discuss in future post.
