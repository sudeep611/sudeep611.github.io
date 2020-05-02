---
layout: post
title:  "Learn Kotlin (Part 3) - Control Flow"
categories: Programming
tags: Kotlin
---
Post Series: <br />
Part 1: [Hello world and Basic Data Types](https://sudeepacharya.com.np/blog/2018/12/03/learn-kotlin-part-1-hello-world-and-basic-data-types/)<br />
Part 2: [Array, Collection and Range](https://sudeepacharya.com.np/blog/2018/12/10/learn-kotlin-part-2-array-collection-and-range/)<br />
Part 3: [Control Flow](https://sudeepacharya.com.np/blog/2018/12/17/learn-kotlin-part-3-control-flow/)<br />
Part 4: [Function](https://sudeepacharya.com.np/blog/2018/12/25/learn-kotlin-part-4-function/)<br />
Part 5: [Class](https://sudeepacharya.com.np/blog/2019/01/09/learn-kotlin-part-5-class/)<br />

In this post we are going to learn about the control flow in Kotlin. Let us learn about how to make a decision, how to perform a task multiple times by iterating and how to get out of the loop, how to continue to next iteration. So, today we will learn all about changing the control flow of Kotlin program.

<h2>If..Else</h2>
When we want to make a decision in program we use if and else. This is not different from other languages like Java. Even the syntax is similar to Java.

However, if is the expression and not the keyword so it returns the value only whenever essential. Let us see the syntax for if..else.

```kotlin
fun main(args: Array<String>) {
    val a : Int = 100
    val b : Int = 200

    if(a > b) {
        println("a is greater than b")
    } else {
        println("b is greater than a")
    }
}
```

Or we can also write without bracket in a single line like this:

```kotlin
if(a > b) print("a is greater than b") else print("b is greater than a")
```

In the code above it checks for one condition, here first it checks whether a is greater than b, if not certainly b is greater. But what if both are of same value. We will need one more condition to be checked. So we have else if for checking more condition.

```kotlin
fun main(args: Array<String>) {
    val a : Int = 200
    val b : Int = 200

    if(a > b) {
        println("a is greater than b")
    } else if(a == b) {
        println("a and b are equal")
    } else {
        println("b is greater than a")
    }
}
```

<h2>When</h2>
When in kotlin is similar to the switch in other languages like Java and C++. When is like a branching against one variable, it checks for a variable against values and execute a block of code if it matches the value.

Let us dive in the syntax of when.

```kotlin
fun main(args: Array<String>) {
    val a : Int = 3

    when(a) {
        1 -> println("a is 1")
        2 -> println("a is 2")
        3 -> println("a is 3")
        else -> {
            println("1 is none of 1,2 and 3")
        }
    }
}
```
In the above code we checked for variable a against the values 1, 2 and 3 and finally the else is executed if the value of a is none of them. You might be wondering why use when  when we have if..else. But when got many advantages over if..else, one of them is since this is branching statement, if executes faster and saves the CPU time also the code looks clear.

Next, using else is not compulsory and we can check for multiple values to execute same block of code and also check the range.

```kotlin
fun main(args: Array<String>) {
    val a : Int = 10

    when(a) {
        in 1..7 -> println("a lies in between 1 and 7")
        8,9 -> println("a is either 8 or 9")
        10 -> println("a is 10")
    }
}
```
<h2>For loop</h2>
What if you want to print one line of sentence. You will write

```kotlin
println("Print this line.")
```

Next, what if you want to print 1000 or probably print 10s of thousand times. In this case, it will be madness to write all the print lines line by line. So, this is where the looping comes handy.

Looping is basic and essential part in every programming languages. You might have already done looping in Java or other programming languages. However for loop in kotlin is little different, let us see the syntax.

```kotlin
// For looping in the number range
fun main(args: Array<String>) {
    for(i in 1..10) {
        print(i)
    }
}
```

```kotlin
// For looping in the array
fun main(args: Array<String>) {
    val nums = intArrayOf(19,22,3,67,35)
    for(i in nums) {
        println(i)
    }
}
```
<h2>While loop and Do..while loop</h2>
While loop in Kotlin is similar to java, we also have do while loop in Kotlin, while and do..while are entry control and exit control loop. Let us see the example to make us more clear.

```kotlin
fun main(args: Array<String>) {
    var count : Int = 0

    while(count < 5) {
        println(count)
        count += 1
    }
}
```

You will find the syntax similar to Java, and next let us see the syntax of do..while loop.

```kotlin
fun main(args: Array<String>) {
    var count : Int = 0
    do {
        println(count)
        count += 1
    } while(count < 5)
}
```

The differences between while and do..while loop is that, while loop checks the condition before entering into the loop whereas the do..while loop first executes the code inside the block and then checks for the condition in order to get out of the loop.

<h2>Return, Continue and Break</h2>
These keywords have similar use in Kotlin as that of any other programming languages such as Java.

<b>Return</b> – It returns the value from the function.

```kotlin
fun main(args: Array<String>) {
    print(getString())
}

fun getString():String {
    return "I am returned string"
}
```

<h2>Break and Continue</h2>
```kotlin
fun main(args: Array<String>) {
   valuecheck3@ for(x in 1..5) {
      if(x == 3) {
         println("x is 3")
         break@valuecheck3
      } else {
         println("x is not 3")
         continue@valuecheck3
      }
   }
}
```

In the above code, we created the label named <b>valuecheck3</b> and performed a looping to check if the value of x is 3, if value of x is 3 then we break out of loop and if the value of x is not 3 then we continue to loop i.e run label <b>valuecheck3</b>.

So, in this post we discussed control flow including looping and branching statements. In the next post we will be diving into other topics. Keep writing in Kotlin.
