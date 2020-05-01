---
layout: post
title:  "A Silly way to comment in your Code"
categories: Programming
tags: PHP
---
During my beginners year of writing code, i used to comment unnecessarily. I realised this after i saw the code written by senior developers. The main purpose of the comment is to make your code understood by other developers who are working together in the same project or for other contributors.

Let us take an example of the silly code:

```php
<?php

// Assigning the value to firstNumber
firstNumber = 9

// Assigning the value to secondNumber
secondNumber = 12

// Creating variable to store the sum of firstNumber and secondNumber
sumOfNumbers = 0;

// Adding both firstNumber and secondNumber and storing it to sumOfNumbers
sumOfNumbers = firstNumber + secondNumber

// Displaying the result
echo sumOfNumbers;
?>
```

Read the code above, how do you feel about that?

The person who will read your code will be developer or some one who understands the code. If he does not understand that firstNumber = 9 is assigning number 9 to variable firstNumber, then he needs to learn programming. It is not your job to make him understand this.

However, this commenting style might be helpful if you are University Professor teaching how-to-write-code to your student.

So, the better version of the above code would be like this:

```php
<?php
firstNumber = 9
secondNumber = 12
sumOfNumbers = 0;
sumOfNumbers = firstNumber + secondNumber
echo sumOfNumbers;
?>
```

Much better isn't it?

So, unless you are teaching programming to someone beginners don't write unnecessary comment in your code for two reasons. First one is it makes code unreadable to some sense. Next one is other programmers thinks you are silly because you think they are silly.
