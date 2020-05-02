---
layout: post
title:  "Learn Kotlin (Part 5) - Class"
categories: Programming
tags: Kotlin
---
Post Series: <br />
Part 1: [Hello world and Basic Data Types](https://sudeepacharya.com.np/blog/2018/12/03/learn-kotlin-part-1-hello-world-and-basic-data-types/)<br />
Part 2: [Array, Collection and Range](https://sudeepacharya.com.np/blog/2018/12/10/learn-kotlin-part-2-array-collection-and-range/)<br />
Part 3: [Control Flow](https://sudeepacharya.com.np/blog/2018/12/17/learn-kotlin-part-3-control-flow/)<br />
Part 4: [Function](https://sudeepacharya.com.np/blog/2018/12/25/learn-kotlin-part-4-function/)<br />
Part 5: [Class](https://sudeepacharya.com.np/blog/2019/01/09/learn-kotlin-part-5-class/)<br />

Although Kotlin is statically typed language, it supports object-oriented programming like Java. Before explaining further let us dive into the basic syntax of the Kotlin class.

```kotlin
class Vehicle { // class definition
    // class body
}
```
So, defining a basic class is as simple as this and similar to Java.

Before diving further into the class syntax let us first discuss about the four access modifier available in Kotlin.

<h2>Access Modifier</h2>

<b>Public :</b> A publicly defined entity is accessible from anywhere in or outside the class. It is similar to what public access modifier was like in Java. If no access modifier is define then by default it is public.

<b>Private :</b> If something is private then it can be accessed within the enclosing scope. For example if class in private then only the same file can access it. Next, if variable within class is private then it can be accessed only from the class.

<b>Protected :</b> If something is protected in the main class then it can be accessed by the sub-classes as well.

<b>Internal :</b> This is newly introduced in Kotlin which is not available in Java. If anything is define Internal then it limits the visibility within the same module. So, this creates the visibility in the package/module level.

<h2>More on Kotlin Class</h2>
Let us start by seeing more complete class with a function/method and attribute.

```kotlin
class Dog {
    private var numberOfLegs = 4

    fun startBarking() {
        println("Barking!")
    }
}

fun main(args : Array<String>) {
    val d = Dog() // Creating an object
    d.startBarking() // calling the class function
}
```

<h2>Nested Class</h2>
The class in the kotlin can be written inside the class, which is called the nested class. This is similar to what we had done in functions like defining the function inside the function. Let us see one example of nested class:

```kotlin
fun main(args: Array<String>) {
   OuterClass.NestedClass().sayHello()
}
class OuterClass {
   private var name: String = "Sudeep"
   class NestedClass {
      fun sayHello() {
          print("Hello! Sudeep")
      }
   }
}
```
Here, if you try to access the variable name from the NestedClass then it will throw the error. Next, we have inner class where you can access the variables of Outer Class inside it.

<h2>Inner Class</h2>
```kotlin
fun main(args: Array<String>) {
   OuterClass().NestedClass().sayHello()
}
class OuterClass {
   private var name: String = "Sudeep"
   inner class NestedClass {
      fun sayHello() {
          print("Hello! " + name)
      }
   }
}
```

So, we can now access the variable of the outer class inside the inner class as well and notice the difference in the calling the Nested Class function in line 2.

<h2>Anonymous Inner Class</h2>
Anonymous inner class are useful while creating and instantiating the object. For example let us see one example:

```kotlin
fun main(args: Array<String>) {
   var animal : Dog = object: Dog { // creating an instance of the interface Dog
      override fun bark() { // overriding the bark method
         print("Bark! Bark! bark!")
      }
   }
   animal.bark()
}
interface Dog {
   fun bark()
}
```
Here we can create the object of interface by overriding the function at the same time.

That’s all for this post! Cheers!
