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
<h4>Using inline scripts to add Javascript to a web page</h4>
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
After saving and opening the file, you should see the bold title "<strong>Webpage work!</strong>" when you view that file in a browser. So now let's add some Javascript.

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

<img class="alignnone size-full wp-image-157" src="http://matw.me/wp-content/uploads/2018/11/add-script-inline.png" alt="" width="601" height="532" />
<h4>Adding external Javascript files to a web page</h4>
Inline scripts are OK for smaller sections of code, but are not ideal for larger projects. Using external scripts we can write Javascript in a seperate file and then include it into our page with the same script tags as above, but with one modification. To do this we use an attribute within the script tag which looks like: <code>&lt;script src="file.js"&gt;&lt;/script&gt;</code>. The added "scr" is an abbreviation of source and it defines where the webpage can find the script file. So to add an external script to our example web page, let's <strong>save a Javascript file in the same folder</strong> as our HTML file and name it "example.js". Using our text editor again add the <code>console.log('Hello from Javascript')</code> and let's also add another line, <code>console.log('I am an external script')</code>. So our example.js file should look like:
<pre>console.log('Hello from Javascript')
console.log('I am an external script')
</pre>
Once that is done we need to go back to our HTML file and update our script tag. By having the two files in the same folder we can simply add our Javascript file name to the "scr" attribute. So you HTML file will look like:
<pre>&lt;!DOCTYPE html&gt;
&lt;html&gt;
    &lt;head&gt;
        &lt;title&gt;Hello Javascript&lt;/title&gt;
    &lt;/head&gt;
    &lt;body&gt;
        &lt;h1&gt;Webpage works!&lt;/h1&gt;
        &lt;script src="example.js"&gt;&lt;/script&gt;
    &lt;/body&gt;
&lt;/html&gt;</pre>