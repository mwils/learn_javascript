---
ID: 57
post_title: >
  How to Write Your First Function In
  Javascript
author: Matthew Wilson
post_excerpt: ""
layout: post
permalink: >
  http://matw.me/index.php/2018/11/08/how-to-write-your-first-function-in-javascript/
published: true
post_date: 2018-11-08 18:02:19
---
<h4>Functions are the basic building block of programming</h4>
Now for the real meat of programming, functions. Functions are named sections of code that combine operations to perform a certain procedure. Functions can accept inputs and may return a value (an output). In the <span style="color: #000080;"><u><a href="http://matw.me/index.php/2018/11/03/a-load-of-objectionable-content/">previous post</a></u></span>, we started a bank and our first customer, John, deposited $500. Whenever John made a transaction, we had to add or subtract the transaction from his balance manually. This is a perfect use case for a function. By the end of this post, <span style="color: #000000;">you should </span>understand how to write a function that can do <span style="color: #000000;">exactly </span>that.
<h4>A very basic function</h4>
<img class="size-medium wp-image-93 alignleft" src="http://matw.me/wp-content/uploads/2018/11/anatomy_of_a_function2-300x188.png" alt="" width="300" height="188" />

Let's start by making a very basic function that calculates a tip for us. Given we want to always tip an even 15%, this is an <span style="color: #000000;">extremely </span>simple function to write. To calculate this in the console would just be <code class="western">cost * .15</code>, but now, let's make a function. We can declare a function with the var keyword, just like we declared strings, arrays, and objects. The var keyword is followed by the function name, an equal sign and then the function's body. Let's call our tip calculator function, "getTip". Since our tip is based on the cost of a service or meal, our function will need a way to accept that value as an input. Parameters are used to provide inputs to functions and we will need to input the meal cost, so let's make a parameter called “cost”. Now, our function would look like this: <code class="western">var getTip = function (cost) { return cost * 0.15 }</code>. The return keyword causes whatever follows it on the same line to be "outputted" from the function, but the return keyword also stops further execution of code. Try creating this function in the console (<span style="color: #000080;"><u><a href="http://matw.me/index.php/2018/10/25/the-beginning/">see how to open here</a></u></span>). After the function is declared, it's stored under the named variable you assigned it to. So, if you used getTip, you can type getTip, followed by enter to see <span style="color: #000000;">that </span>it has successfully been declared as a function. This will not execute the function, but simply display it in the console.
<h4>Invoke a function</h4>
<img class="size-medium wp-image-96 alignright" src="http://matw.me/wp-content/uploads/2018/11/tip-calc-func-300x217.png" alt="" width="300" height="217" />

<span style="font-family: inherit, serif;">Now to invoke a function, we enter the function's name followed by a set of parentheses. Inside the parentheses, we place the value (or values) of our parameters. So, to calculate a tip for a $50 meal, we would use </span><code class="western">getTip(50)</code><span style="font-family: inherit, serif;">. This will “return” </span><span style="font-family: inherit, serif;">(“return” is the output of a function)</span><span style="font-family: inherit, serif;"> us the tip amount, or in this case, 50 * 0.15, </span><span style="color: #000000;"><span style="font-family: inherit, serif;">which is </span></span><span style="font-family: inherit, serif;">7.5.</span>
<h4>Bank deposit function</h4>
Our getTip function takes a parameter "cost", performs a calculation using this parameter and then returns a value; however, not all functions must return a value. Some functions can perform an action and modify an existing object, but return nothing. In a previous post we used a bank as an example, let’s use that example again. First declare the bank object, <code class="western">var bank = {}</code>, and then we can add John's account directly <code class="western">bank.john = { accountType: "savings", balance: 500 }</code>. This is slightly different than how the account was created in the previous post, but it does the same thing. Now, if we type bank and hit enter, we should see our bank object with John's account on it. Great, our bank is loaded. Next, let's create a function named deposit, that will make a deposit to John's bank account. We can name this function "deposit", and it will take the balance in John's account and add to it whatever amount is passed into the parameter "amount". Thus, it would look like:
<pre class="western">var deposit = function (amount) {
  bank.john.balance += amount
}</pre>
We timed that perfectly, as John just won the lottery and is here to deposit his $1,000,000 winnings. Let's give it a try <code class="western">deposit(1000000),</code> and now we need to check John's account balance, <code class="western">bank.john.balance</code>. Wow, that worked great, John's balance is now $1,000,500, and we didn't have to do any manual update to his account balance. However, there is a problem here: this function works great if we only have one customer, but most banks have multiple customers, and they will not be happy if every time they each make a deposit, it winds up in John's bank account. Fortunately, there are a lot of great solutions for this problem, and in future posts, we will cover fun and useful concepts like classes and inheritance that solve this and similar problems.
<h4>Practice</h4>
OK, in the comment sections, see if you can create functions to do some <span style="color: #000000;">of the following</span>:
<ul>
 	<li>Multiply a number by 2</li>
 	<li>Square a number</li>
 	<li>Make a greeting function that takes someones name and returns "Hello, [name here]."</li>
 	<li>Function to withdraw from an account</li>
 	<li>A function to add interest into a bank account</li>
 	<li>Or another problem you can think of</li>
</ul>