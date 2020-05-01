---
layout: post
title:  "Understanding Decorators in Python"
categories: Programming
tags: Python
---
While learning Python in the beginning, i skipped the portion of the chapters on Decorators. After i worked on Flask and Django, I was introduced with the Decorators.

Let us consider a simple flask app example:

```python
@app.route("/")
def hello():
    return "Hello World!"
```

In this code the line with @ symbol is decorators. Decorators is one of the important feature in Python that you must learn to master it. It is not that hard, so let us learn it.

<strong>First let us see Closures</strong>

```python
>>> def out_func():
...     def in_func():
...             print("I am inner function")
...     return in_func
...
>>> call = out_func()
>>> call
<function in_func at 0x7f0d6819a758>
>>> call()
I am inner function
>>>
```

Also let us see by passing the parameter in the function.
```python
>>> def out_func():
...     def in_func(x):
...             print(x)
...     return in_func
...
>>> call = out_func()
>>> call
<function in_func at 0x7f66ff93f5f0>
>>> call(3)
3
>>>
```

We can also pass the function as the parameter in the function. Let us write a function wrap which takes a function. We write another function checkNumber inside the wrap. It's main task is to return same number if the number is greater than or equal to 100 otherwise return number by adding 100. It actually adds 100 using function that we pass to wrap.

We also write function incrementHundered to add 100 to passed number.

```python
def wrap(func):
   def checkNumber(a): # check
       return (a if a >= 100 else func(a))
   return checkNumber

def incrementHundered(a):
    return a+100

# We pass incrementHundered to wrap
incrementHundered = wrap (incrementHundered) # decorators

print (incrementHundered(2)) # 102
print (incrementHundered(300)) # 300
print (incrementHundered(29)) # 129
```

The above code can be re-written using @ symbol for decorators as follows:

```python
def wrap(func):
   def checkNumber(a): # check
       return (a if a >= 100 else func(a))
   return checkNumber

@wrap
def incrementHundered(a):
    return a+100

print (incrementHundered(2)) # 102
print (incrementHundered(300)) # 300
print (incrementHundered(29)) # 129
```

By writing @wrap and function just below it, think as if we have passed whole function to wrap. And it works as usual. So that was the quick and easy introduction to Decorators.

I hope you understood the Decorators.
