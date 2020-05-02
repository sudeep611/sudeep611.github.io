---
layout: post
title:  "Learn Kotlin (Part 2) - Array, Collection and Range"
categories: Programming
tags: Kotlin
---
Post Series: <br />
Part 1: [Hello world and Basic Data Types](https://sudeepacharya.com.np/blog/2018/12/03/learn-kotlin-part-1-hello-world-and-basic-data-types/)<br />
Part 2: [Array, Collection and Range](https://sudeepacharya.com.np/blog/2018/12/10/learn-kotlin-part-2-array-collection-and-range/)<br />
Part 3: [Control Flow](https://sudeepacharya.com.np/blog/2018/12/17/learn-kotlin-part-3-control-flow/)<br />
Part 4: [Function](https://sudeepacharya.com.np/blog/2018/12/25/learn-kotlin-part-4-function/)<br />
Part 5: [Class](https://sudeepacharya.com.np/blog/2019/01/09/learn-kotlin-part-5-class/)<br />

In this post we will discuss about the Array, Collection and Range in Kotlin.

<h2>Array</h2>
In Kotlin, we can create array using two different ways. First one is by using <b>arrayOf()</b> function and next one is by using <b>Array()</b> constructor.

<h2>Using arrayOf() function</h2>
```kotlin
val accountInfo = arrayOf("Sudeep", 34000)
```

The accountInfo array is of type Array<Any>. It holds array with two different types of element String and Int, next there are functions like intArrayOf(), charArrayOf(), booleanArrayOf(), longArrayOf(), shortArrayOf(), byteArrayOf().

th two different types of element String and Int, next there are functions like intArrayOf(), charArrayOf(), booleanArrayOf(), longArrayOf(), shortArrayOf(), byteArrayOf().

For example using intArrayOf(3,4,5,6) make an array of type integer with the given numbers. If you try of push some other types of data into the int array then it will throw compile error.

Alternatively you can use arrayOf<Int> instead of intArrayOf.

```kotlin
val num1 = arrayOf<Int>(3,4,5,6)
val num2 = intArrayOf(3,4,5,6)
```

<h2>Using Array() constructor</h2>
Another way of making array is by using Array() constructor. This function takes two parameter, first one is the size of the array and next one is the lambda function to create the values.
```kotlin
val numbersArray = Array(5, { i -> i * 3 })
```

<h2>Collections : List, Set, Map</h2>
In kotlin, you can either create mutable or immutable collections. Collections include list, set and map in kotlin.

<h2>List</h2>
To create immutable list we use the following syntax:

```kotlin
val iMutNumbers: List<Int> = listOf(3,4,5,6)
```

You cannot edit this list afterwards, if you want to make the list which you can edit later then you should create the mutable list. We use the following syntax to create mutable list:

```kotlin
val mutNumbers: MutableList<Int> = mutableListOf(1,3,4,5)

// You can add item to this list by using add function
mutNumbers.add(9)
```

Similarly, we can create list of String, Boolean, long and so on.

We can use <b>emptyList()</b> function to create immutable list:

```kotlin
val emptyList: List<String> = emptyList<String>()
```

Next we have <b>listOfNotNull()</b> function to create list with non-null element.

<b>arrayListOf()</b> creates a mutable list.

<h2>Sets</h2>
It is an unordered collections of unique element. One of the way to create set is by using setOf() function.

```kotlin
val mixedTypeSet = setOf(4,5,"Pokhara")
val intOnlySet: Set<Int> = setOf(3,4,5,6)
// This creates immutable set
```

Another way to create set which is mutable is using hashSetOf() function.

```kotlin
val intsHashSet: java.util.HashSet<Int> = hashSetOf(1, 2, 6, 3) intsHashSet.add(5)
intsHashSet.remove(1)
```

<b>sortedSetOf()</b> creates mutable set which is sorted by using operator.

<b>linkedSetOf()</b> maintains the order in which the items are inserted in the set. It is also mutable.

<b>mutableSetOf()</b> creates the mutable set which is equivalent to Java LinkedHashSet.


<h2>Map</h2>
Map is the data type which store keys and value pair. All the keys are unique for each of the value.  mapOf creates immutable map.

```kotlin
val countryCallingCode: Map<Int, String> = mapOf(977 to "Nepal", 1 to "United States", 61 to "Australia")
for ((key, value) in countryCallingCode) {
    println("The calling code of $value is $key")
}

// It can also be accessed like array
println(countryCallingCode[977])
```

we can use <b>mutableMapOf()</b> function in order to create the mutable map.

<b>hashMapOf()</b> creates mutable hash map. Hash map class uses a hash table to implement the Java map.

<b>linkedHashMap()</b> stores the data in the order in which they were inserted.

<b>sortedMapOf()</b> stores the data in sorted order.

<h2>Range</h2>
Range is special data type in kotlin. For example:

```kotlin
var numOneToFive = 1..5

for(i in numOneToFive) {
    print(i)
}
```

Similarly works for character.

```kotlin
var alphabets = 'a'..'g'

for(i in alphabets) {
    print(i)
}
```

In the range the starting and the ending values are inclusive. We can use <b>rangeTo()</b> function instead of <b>..</b>

```kotlin
val oneToFive: IntRange = 1.rangeTo(5)
```

Next we can use <b>downTo()</b> function to make list of numbers starting from higher to lower range.

```kotlin
val tenToOne = 10.downTo(1)
```

We can also make a range using some gap. For example to create the range of numbers 1,3,5,7,9 we can use <b>step</b> keyword.

```kotlin
val oneToTenStep = 1..10 step 2
```

Lastly, if we want to check if a element in inside the range we can use <b>in</b> keyword.

```kotlin
if(4 in tenToOne) {
 print("4 exists in the range.")
}
```

So, this is all for this post. We learned about Arrays, collection and range in kotlin. We will dive more into Kotlin in the further post.
