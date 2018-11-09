---
ID: 37
post_title: >
  How to Create Arrays and Lists in
  Javascript
author: Matthew Wilson
post_excerpt: ""
layout: post
permalink: >
  http://matw.me/index.php/2018/10/29/an-array-of-variety/
published: true
post_date: 2018-10-29 22:19:49
---
In the previous post, we went over strings and variables, but we need methods to organize our strings and variables. If we were going to the grocery store, we would not write bananas on one piece of paper, bread on another, milk, eggs, cheese, etc each on separate pieces of paper. This would become very disorganized quickly. Instead, we create a list. Javascript has something very similar to a list called an array.
<h4>Grocery list</h4>
<img class="size-medium wp-image-49 alignleft" style="color: var(--color__text); font-family: inherit;" src="http://matw.me/wp-content/uploads/2018/10/groceries-300x133.png" alt="" width="300" height="133" />

Let's create a list called groceries. Let's do this in the Chrome devTools console tab. How to open the console was covered in this <span style="color: #000080;"><u><a href="http://matw.me/index.php/2018/10/25/the-beginning/">post here</a></u></span>. To make our grocery list we need to declare a new variable. Just like when we declared our string variable in the <span style="color: #000080;"><u><a href="http://matw.me/index.php/2018/10/27/string-theory/">previous post</a></u></span>, we will use the var keyword. However, to create the list we need to use a pair of square brackets []. We can make an empty list like this: <code class="western">var groceries = []</code>, but this isn't very useful. In order to have things in our list, we add them inside our brackets and separate them with a comma. Strings still need to be in quotes, so a list with milk and bread would look <span style="font-family: inherit, serif;">like:</span>  <code class="western">var
groceries = ["milk", "bread"]</code><span style="font-family: inherit, serif;">. Go ahead and give that a try, type that in and press enter. Now to see your list again, you can type </span><code class="western">groceries</code> <span style="font-family: inherit, serif;">and hit enter.</span>
<h4>Array of Numbers</h4>
Arrays can also hold numbers. Creating an array with a number is the same as with a string except you don't place numbers in quotes. For example, <code class="western">var </code><code class="western">lottery</code><code class="western">Numbers
= [4, 8, 15, 16, 23, 42]</code>.
<h4>Other useful array features</h4>
Arrays have some cool features that make them very useful. An array can tell you how many items it has with the length property. To check the length of our groceries list, we would use <code class="western">groceries.length</code>. The dot here allows us to access the "Sub" properties of the array. The length is a property of all Javascript arrays. Along with length, arrays have a few functions that are also accessible by using "dot" after the array name. One of the most useful allows us to search an array to find the position of a sp<span style="font-family: inherit, serif;">ecific entry (element). This property is called “findIndex”. Since it is a function, it has to be invoked. Functions in Javascript are invoked with a pair of parenthesis immediately after the function's name. For example, if we had a list of students ordered by class rank, and we wanted to know John's position, given the array </span><code class="western">var
students = ["Mary", "John", "Steve",
"Bob"]</code> <span style="font-family: inherit, serif;">(Looks like the parents of these students were not very creative in naming their children), we could enter students.indexOf("John") to find that John's index is 1. Well, that may not have been what you expected, since Mary is the first student, but our indexes start with 0. So Mary's index would be 0 and John's would be 1.</span>

<img class="size-medium wp-image-53 alignleft" style="color: var(--color__text); font-family: inherit;" src="http://matw.me/wp-content/uploads/2018/10/indexof-300x95.png" alt="" width="300" height="95" />

I

f the item is not found, findIndex returns -1. It's a common operation to use this in order to check if an item is in an array. The logic looks like this: "if findIndex of needle in haystack is -1 then the needle is not present".

Arrays come with a lot of other properties and built-in functions. Check out <span style="color: #000080;"><u><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array">this list on MDN</a></u></span> to see what else an array can do. I'll cover arrays in more detail in a later post.

Feel free to use the comment section to create some array examples.