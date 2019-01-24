---
ID: 232
post_title: Using JavaScript to Select HTML Elements
author: Matthew Wilson
post_excerpt: ""
layout: post
permalink: >
  http://matw.me/index.php/2019/01/23/using-javascript-to-select-html-elements/
published: true
post_date: 2019-01-23 22:22:13
---
One of the most common uses of JavaScript to manipulate elements on a web page. As we learned in the <a href="http://matw.me/index.php/2018/12/01/how-to-use-javascript-to-interact-with-html-webpage/">interact with the DOM post</a>, the fist step to manipulating an HTML element is selecting it. The document object that is built into web browser's JavaScript provides multiple methods that can be used to select an element.

I think it's important to mention that you will commonly see jQuery mentioned in connection to selecting HTML elements. jQuery is a library (collection of methods and functions) that abstracts many commonly needed actions. I will not cover the use of jQuery in this post as I want to focus mainly on vanilla (plain) JavaScript. Under the hood, jQuery uses the same methods covered here. Old browser versions had inconsistencies in the document object and it's methods that jQuery helped resolve. Most of these issues have been resolved and the methods covered here are included and standardized across all modern web browsers.

It is assumed that you have a basic understanding of HTML and CSS. If not, then you may find the following difficult to follow. I have placed some <a href="http://matw.me/index.php/links-and-resources/">excellent HTML and CSS links here</a> that will aid your HTML learning.
<h6>getElementById</h6>
<span style="color: var(--color__text); font-family: inherit;">The method getElementById is the easiest selector method to use. As the name suggests, it finds an element by using its id. Because every ID on valid HTML a page is unique, you know exactly what element it is returning. Of course the element you want to get must have an ID.</span>

The getElementById method takes a string for a parameter and returns the element directly.

Take a look at this interactive code snippet:
<p class="codepen" data-height="300" data-theme-id="light" data-slug-hash="KbyWYB" data-default-tab="html,result" data-user="matw" data-pen-title="KbyWYB">See the Pen <a href="https://codepen.io/matw/pen/KbyWYB/">KbyWYB</a> by Matthew Wilson (<a href="https://codepen.io/matw">@matw</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

We have an HTML paragraph with an ID of "foo". To select this element we use the method getElementById and insert the name of the ID (in our case "foo") as the first and only parameter. <code>var mySelectedElement = getElementById("foo");</code>.

So now mySelectedElement is set to our HTML element. Our element has many properties, but since in this example we want to change the color we need to update style.color. This can be reassigned to change the elements color and in our example we set it to equal "red". <a href="http://matw.me/index.php/2019/01/23/methods-and-properties-of-html-elements/" target="_blank" rel="noopener">If you are curious about the other properties on HTML elements see my post here.</a>
<h6>getElementsByClassName</h6>
Because many elements on a page do not have an id, I find myself using getElementsByClassName a lot more frequently than getElementById. As you might guess from the name, this method returns an array-like-object that contains a collection of elements. This is unlike getElementById which directly returns one element. This means that if you are wanting to select one particular element, you will need to select it from your returned object, however in many cases you may want to perform an action on multiple elements. If this is the case and all your elements have the same class, then the getElementsByClassName works out well.

Let's look at an example. Say we have a list of names and passwords and we want to hide the passwords on the click of a button. We could do something like this:
<p class="codepen" style="height: 420px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid black; margin: 1em 0; padding: 1em;" data-height="420" data-theme-id="light" data-default-tab="html,js,result" data-user="matw" data-slug-hash="LqPZEr" data-pen-title="Using getElementsByClassName example">See the Pen <a href="https://codepen.io/matw/pen/LqPZEr/">
Using getElementsByClassName example</a> by Matthew Wilson (<a href="https://codepen.io/matw">@matw</a>)
on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

The <code>document.getElementsByClassName('secret')</code> returns an object populated with all the elements that have the class "secret". We can then use a <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of">for..of loop</a> to change the style of each element.

You should also know that getElementsByClassName can be called, not only from the document object, but from any element. It is important to note that it only finds matches that are children of the calling element's node. This behavior is useful in many situations. Extending the previous example, let's make our password list have several sections that can be hidden individually. Also let's reverse the action, instead of hiding our passwords, let's reveal them on click.
<p class="codepen" style="height: 520px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid black; margin: 1em 0; padding: 1em;" data-height="520" data-theme-id="light" data-default-tab="html,result" data-user="matw" data-slug-hash="aXzpqL" data-pen-title="Using getElementsByClassName with children">See the Pen <a href="https://codepen.io/matw/pen/aXzpqL/">
Using getElementsByClassName with children</a> by Matthew Wilson (<a href="https://codepen.io/matw">@matw</a>)
on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

There are a few things here that at first may not be clear, so let's take a closer look. We are using a special keyword "this" as the first parameter in our on-click handler. If you look at the HTML you will see our button section looks like <code>&lt;button onclick="showSecrets(this)"&gt;HIDE SECRETS&lt;/button&gt;</code>. Here the "this" is actually sending in the button element as a parameter to the <code>showSecrets</code> function. Now we have our calling element inside our function and can use that to our advantage. Since our button and our list items both have a common parent element (the surrounding div) we can use that parent element to call getElementsByClassName and reveal only the passwords in that section.

As you can see from this example, we can use getElementsByClassName's descendant-only matching behavior to our advantage. If it found every match on the page, we would have to use separate class names or another method to select only one section of passwords to reveal.
<h6>Coming soon - Part 2
getElementsByTagNames &amp; querySelector</h6>