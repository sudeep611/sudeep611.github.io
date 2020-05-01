---
layout: post
title:  "JavaScript code to display Multiplication table"
categories: Programming
tags: JavaScript
---

Through JavaScript you can easily write the html code in html document using document.write(). Using document.write() and for loop it is easy to print the table of user input number.

First of all "prompt" box will appear and then this value will be parse to integer and the multiplication table is displayed.

The source code for JavaScript is as follows:

```javascript
<script type='text/javascript'>
var num = prompt("Enter Number", "0") //prompt user to enter the number

var num = parseInt(num); //parse the num to number
var i = 0;

document.write('<table border="1" cellspacing="0">');
for(i=1;i<10;i++) {
    document.write("<tr><td>" + num + " x " + i + " = " + num*i + "</td></tr>");
}

document.write("</table>");
</script>
```
