---
ID: 20
post_title: >
  Javascript String Basics, How to Make
  and Edit Strings
author: Matthew Wilson
post_excerpt: ""
layout: post
permalink: >
  http://matw.me/index.php/2018/10/27/string-theory/
published: true
post_date: 2018-10-27 21:36:24
---
<h4>Strings</h4>
Strings are sequences of characters. In the previous <span style="color: #000080;"><u><a href="http://matw.me/index.php/2018/10/25/the-beginning/">post</a></u></span>, we saw how to open the Chrome devTool inspector panel. In the console tab, we can enter numbers and use the console as a basic calculator. When dealing with numbers in Javascript, we do not place quotes around them, but when entering strings, they must begin and end with a quotation mark. The quotation mark can be a single <code class="western">'</code> or a double <code class="western">"</code> quotation mark. For example, to create a string with the text Hello World, type <code class="western">"Hello World"</code> into the console then the return key to execute. This will cause the string <code class="western">"Hello
World"</code> to be repeated in the console. What's happening here is the line is actually read in, then Javascript produces an actual string and then returns it. This returning of the string is what produces the second output of <code class="western">"Hello
World"</code>. The string is returned, but it is never saved, so it just vanishes in this example.
<h4>Declaring String Variables</h4>
Well, the previous example was not very useful - a string is created and then vanishes. To improve on this and do something a bit more useful, we need to save the string somehow. This is done by declaring a variable and the string as the variable's value. Variables are declared with the keyword <code class="western">var</code> followed by the variable name. For example, to declare a variable named myString, type <code class="western">var myString</code> followed by enter. This will create a variable, yet the variable has no set value. The equal sign is used to set the variable’s value and the syntax to set a string value looks like variableName = "value". So for our example, setting myString to Hello World, type <code class="western">myString = "Hello World"</code> followed by enter. It is possible to combine the variable declaration and setting into one command like this <code class="western">var
myString = "Hello World"</code>.
<h4>Using Variables</h4>
OK, so the variable is declared and set, but it’s still not useful unless we can do something with the variable. Let's declare one more variable named, <code class="western">myName</code> and set it to "My name is ______" but go ahead and put your name there. So for me, it would look like <code class="western">var myName
= "My name is Matthew"</code> and then enter. Next, let's put the two strings together. This is called concatenation. This is done using the + sign. Technically the + sign here is an operator, as it performs an operation. So putting the two together looks like <code class="western">myString + myName</code>. Go ahead and try it. Well, that's not quite correct - it returns "Hello WorldMy name is Matthew". That's pretty close, but some spacing would help us out. Let reassign (update) the myString variable. Let’s add a period and a space to it. This can be done by simply reassigning it as <code class="western">myString = "Hello World. "</code>, but I'm lazy and don't want to retype “Hello World” again. Instead, I can use a special operator call the concatenation operator which looks like +=. The += operator concatenates two string variables together and updates the first variable to the concatenated string. An example should help clear that explanation up. So continuing with our previous example, to update myString by adding a space and a period, we can simple use <code class="western">myString
+= " ."</code> . Don't leave out those quotes! So if we did all that correctly we should be able to do <code class="western">myString
+ myName</code> ENTER and see "Hello World. My name is Matthew".
<h4>Something neat</h4>
Let's try something fun. In your Chrome devTools console, enter <code class="western">document.title = "Kittens"</code>. Now look at the top of the browser, and look at the tab title for the site. It now says Kittens. You just updated the document title with a new string.

So you now can “hack” and change the title of a website. Do you know any other string hacks? Leave a comment if you do.