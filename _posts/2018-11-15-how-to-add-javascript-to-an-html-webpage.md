---
ID: 132
post_title: How to Add Javascript to an HTML Webpage
author: Matthew Wilson
post_excerpt: ""
layout: post
permalink: >
  http://matw.me/index.php/2018/11/15/how-to-add-javascript-to-an-html-webpage/
published: true
post_date: 2018-11-15 21:43:57
---
Until recently using Javascript meant that you were going to use it on a website, however Javascript runs everywhere today. Still the most obvious use for Javascript is to manipulate websites or make a web based application. There are two ways Javascript code can be loaded / added to a webpage, inline or external scripts.

<em>Following along and practicing these examples will help you a great deal in learning Javascript. You will need a simple <strong>text editor</strong> to make your website files. A word processor adds hidden tags to format documents, and while these tags are useful for producing formatted documents, they are not compatible with HTML. You can open a valid HTML file with your browser. There are a few ways to do this, and the easiest way is to right click the file and use "Open With" to open the file with a web browser. For more information visit https://www.codecademy.com/articles/local-web-page</em>
<h4>Using inline scripts to add Javascript to a page</h4>
Let's open our editor and create a basic webpage using the following code...
<pre>&lt;!DOCTYPE html&gt;
&lt;html&gt;
    &lt;head&gt;
        &lt;title&gt;Hello Javascript&lt;/title&gt;
    &lt;/head&gt;
    &lt;body&gt;
        &lt;h1&gt;Webpage works!&lt;/h1&gt;
    &lt;/body&gt;
&lt;/html&gt;</pre>
You should see the bold title "<strong>Webpage work!</strong>" when you view that file in a browser. So now let's add some Javascript.

Javascript can be added directly to an HTML webpage by adding it inside script tags<code>&lt;script&gt; /*javascript code goes here */</code><code>&lt;/script&gt;</code>. There is a function <code>console.log</code> that allows us to output values to the console. Let's use it in our first script. Inside our previous HTML code let's insert a set of script tags with <code>console.log('Hello from Javascript')</code> inside. So now our completed HTML looks like:
<pre>&lt;!DOCTYPE html&gt;
&lt;html&gt;
    &lt;head&gt;
        &lt;title&gt;Hello Javascript&lt;/title&gt;
    &lt;/head&gt;
    &lt;body&gt;
        &lt;h1&gt;Webpage works!&lt;/h1&gt;
        &lt;script&gt;
            console.log('Hello from Javascript')
        &lt;/script&gt;
    &lt;/body&gt;
&lt;/html&gt;</pre>
Now open that page in a web browser and with the console open you should see the words, "Hello from Javascript".

... to be continued...