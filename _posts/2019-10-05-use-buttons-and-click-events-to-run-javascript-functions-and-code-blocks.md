---
ID: 310
post_title: >
  Use Buttons and click events to run
  Javascript functions and code blocks
author: Matthew Wilson
post_excerpt: ""
layout: post
permalink: >
  http://matw.me/index.php/2019/10/05/use-buttons-and-click-events-to-run-javascript-functions-and-code-blocks/
published: true
post_date: 2019-10-05 13:55:46
---
The previous post showed how to select and edit every paragraph element on a page adding a smiley face to each paragraph, but we run the code by entering it directly in the Javascript console. How can we run a section of JavaScript code when something happens? Often we want a section of JavaScript code to run when a button is clicked. Let's see how that is done.

<em>Note that I am ignoring some best practices for the sake of simplicity.</em>

Let's add a button to our page using, <code>&lt;button&gt;CLICK ME&lt;/button&gt;</code>. When we click the button, nothing happens.

<em>Let's say you got here and want to follow these instructions, but don't know how. You can edit, create, and run HTML / Javascript code and html sections at: <a href="https://codepen.io/pen/">https://codepen.io/pen/</a></em>

<button>CLICK ME</button>

Well that does nothing and is pretty boring, so let's make it do something.

Starting simple let make the button trigger an alert. Change the button code to:
<code>&lt;button onclick="alert('You clicked the button')"&gt;CLICK ME!&lt;/button&gt;</code>
to get this:

{{CODE_BUTTON_ALERT}}

If you click on the button, you should get an alert box.

Now let's make a button to add :) to the end of each paragraph.

From the <a href="http://matw.me/index.php/2019/10/05/using-javascript-to-manipulate-a-webpage-using-tag-names-getelementsbytagname/">previous post</a> we have this section of code that appends :) to the end of each paragraph on a website.
<pre>allPTags = document.getElementsByTagName('p'); // Gets all our p tags
for (let pTag of allPTags) { // Loops through each p tag
  pTag.append(' :) '); // Add :) to each P tag
}
</pre>
Let's take this code block and smash it inside our button.
<pre>&lt;button onclick="
  allPTags = document.getElementsByTagName('p'); // Gets all our p tags
  for (let pTag of allPTags) { // Loops through each p tag
    pTag.append(' :) '); // Add :) to each P tag
  }
"&gt;CLICK ME FOR SMILES!&lt;/button&gt;
</pre>
OK, I know this is really ugly, but it's simple and it will work! We can clean this up in a later post.

Here is the result:

{{CODE_BUTTON_SMILE}}

Click away! You will see that every click adds more smiles to the page!