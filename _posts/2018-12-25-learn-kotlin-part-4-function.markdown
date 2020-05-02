---
layout: post
title:  "Learn Kotlin (Part 4) - Function"
categories: Programming
tags: Kotlin
---
Post Series: <br />
Part 1: [Hello world and Basic Data Types](https://sudeepacharya.com.np/blog/2018/12/03/learn-kotlin-part-1-hello-world-and-basic-data-types/)<br />
Part 2: [Array, Collection and Range](https://sudeepacharya.com.np/blog/2018/12/10/learn-kotlin-part-2-array-collection-and-range/)<br />
Part 3: [Control Flow](https://sudeepacharya.com.np/blog/2018/12/17/learn-kotlin-part-3-control-flow/)<br />
Part 4: [Function](https://sudeepacharya.com.np/blog/2018/12/25/learn-kotlin-part-4-function/)<br />
Part 5: [Class](https://sudeepacharya.com.np/blog/2019/01/09/learn-kotlin-part-5-class/)<br />

Merry Christmas Guys! The year 2018 is about to end. This have been a great year. Happy New Year 2019, May your new year be filled with Joy and Happiness. This will probably be the last post for this year 2018. Hope to see you all in the next year!

In today's post i am gonna write about Function. If you have been programming in any of the language then you've been making Functions. Functions are the basic building blocks in programming. Let us discuss about the way to making Functions in the Kotlin.

First of all, let us see the basic syntax of the function in Kotlin.

```kotlin
fun getSum(a : Int, b: Int):Int {
	return (a+b)
}
```

The function above named <b>getSum</b> takes two parameter <b>a</b> of type Int and <b>b</b> of type Int which returns type Int.

<b>return</b> statement returns the value from the function. It is similar to the Java or other programming language.

Next, you can also take no parameters and return type in the functions which can be seen in the code below:

```kotlin
fun printString() {
	print("Hello!")
}
```

So, if there is no return type then the default return type is <b>Unit</b> which is similar to void in Java.

We can also write the single-expression function in the following way:

```kotlin
fun sum(a : Int, b : Int) : Int = a + b
```

We can also define the function inside the function as follows:

```kotlin
fun greetName() {
	print("Hello! ")
	fun printName() {
		print("Sudeep")
	}
	printName()
}
```

<h2>Lambda</h2>
If you have ever done functional programming like Haskell then this might be easy for you to understand. Functions in Kotlin can be passed as a value to other function. Higher order function is the function that takes function as a parameter and returns a function. And the Lambdas are the anonymous function.

```kotlin
val greet : (String) -> Unit = {s:String -> print("Namesta! " + s)}
val name:String = "Sudeep"
greet(name)
```

Here we have a lambda <b>greet</b> which is define as a value and contains a function definition. Next, we pass the variable <b>name</b> to this lambda function.

It makes the code shorter and more readable.

<h2>Higher order functions</h2>
As we talked earlier on introduction, these are the functions which takes function as a parameter or return a function.

```kotlin
fun userName() : String = "Sudeep"
fun greetUser(body : () -> String) : String = "Hello! " + body()
print(greetUser { userName() })
```

Here, <b>greetUser()</b> is a function which takes another function <b>userName()</b> and returns a String. The function <b>userName()</b> returns Name of the user.

This is the simplest example of higher order function.

<h2>Inline function</h2>
We can pass the lambda function to another function which is inline function. It is similar to Higher order function.

```kotlin
fun main(args: Array<String>) {
   val lambdaFun:(String)->Unit  = { name :String->print(name)}
   val name :String = "Sudeep"
   greetUser(name , lambdaFun)
}
fun greetUser(name :String, greet: (String)->Unit) {  
   print("Hello! ")
   greet(name)
}
```

Here, we pass the <b>lambdaFun</b> to another function <b>greetUser</b>.

That’s all folks for this post. In the next post we will discuss further about Kotlin.
