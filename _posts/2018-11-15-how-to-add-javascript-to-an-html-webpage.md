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
<p class="p1"><span class="s1">Until recently, using JavaScript meant was reserved strictly to building websites, but today, Javascript runs pretty much everywhere. That being said, the most common application for JavaScript is still to manipulate websites or make a web-based application. There are two ways that JavaScript code can be loaded and/or added to a webpage: inline scripts and external scripts.</span></p>
<p class="p1"><span class="s1">Practicing these examples will help you start your journey of learning JavaScript. You will need a simple text editor to make your website files. Don’t use a word processor, because they adds hidden tags to format documents, and while these tags are useful for producing formatted documents, they are not compatible with HTML. </span></p>
<p class="p1"><span class="s1">To begin, you can open a valid HTML file with your browser. There are a few ways to do this, and the easiest way is to right click the file and use "Open With" to open the file with a web browser. For more information, visit <a href="https://www.codecademy.com/articles/local-web-page"><span class="s2">https://www.codecademy.com/articles/local-web-page</span></a></span></p>

<h4>Using inline scripts to add Javascript to a web page</h4>
Let's open our editor and create a basic webpage using the following code:
<pre>&lt;!DOCTYPE html&gt;
&lt;html&gt;
    &lt;head&gt;
        &lt;title&gt;Hello Javascript&lt;/title&gt;
    &lt;/head&gt;
    &lt;body&gt;
        &lt;h1&gt;Webpage works!&lt;/h1&gt;
    &lt;/body&gt;
&lt;/html&gt;</pre>
<p class="p1"><span class="s1">After saving and opening the file, you should see the bold title "Webpage works!" when you view that file in a browser. So now let's add some JavaScript.</span></p>
<code></code>
<p class="p1"><span class="s1">JavaScript can be added directly to an HTML webpage by adding it inside script tags </span><code>&lt;script&gt; /*javascript code goes here */</code><code>&lt;/script&gt;</code>. There is a function <code>console.log</code> <span style="color: var(--color__text); font-family: inherit;">that allows us to output values to the console. Let's use it in our first script. Let's insert a set of script tags inside our previous HTML code with </span><code>console.log('Hello from Javascript')</code> inside. <span class="s1">Our completed HTML should now look like:</span></p>

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
<p class="p1"><span class="s1">Now open that page in a web browser. With the console open, you should see the words "Hello from JavaScript".</span></p>
<img class="alignnone size-full wp-image-157" src="http://matw.me/wp-content/uploads/2018/11/add-script-inline.png" alt="" width="601" height="532" />
<h4>Adding external Javascript files to a web page</h4>
<p class="p1"><span class="s1">Inline scripts are fine for smaller sections of code, but they are not ideal for larger projects. Thankfully we can solve this problem by using external scripts. To demonstrate this, let’s write some JavaScript in a separate file and then include it into our page with the same script tags as above, but with one modification. </span></p>
<p class="p1"><span class="s1">To do this, we can use an attribute within the script tag which looks like: </span><code style="color: var(--color__text);">&lt;script src="file.js"&gt;&lt;/script&gt;</code><span style="color: var(--color__text); font-family: inherit;">. </span><span class="s1">The "src" stands for source, and it defines where the webpage can find the script file. So to add an external script to our example web page, let's save a JavaScript file in the same folder as our HTML file and name it "example.js". Using our text editor again, add the </span><code style="color: var(--color__text);">console.log('Hello from Javascript')</code> <span class="s1">. Let's also add another line, </span><code style="color: var(--color__text);">console.log('I am an external script')</code><span style="color: var(--color__text); font-family: inherit;">. So our example.js file should look like:</span></p>

<pre>console.log('Hello from Javascript')
console.log('I am an external script')
</pre>
<p class="p1"><span class="s1">Once that is done, we need to go back to our HTML file and update our script tag. By having the two files in the same folder, all we have to do is add our Javascript file name to the "scr" attribute. So your HTML file will look like:</span></p>

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
<p class="p1"><span class="s1">As long as we entered everything correctly and the files are in the same folder, opening the HTML file with a web browser should look like:</span></p>
<img class="alignnone size-full wp-image-159" src="http://matw.me/wp-content/uploads/2018/11/external-1.png" alt="" width="601" height="530" />
<p class="p1"><span class="s1">You can see both of the console.log statements printed their values into the console. It’s important to note, however, that if the file was in a different location or named incorrectly, our browser would try to load the file but would return an error instead. This would look like:</span></p>
<img class="alignnone size-full wp-image-160" src="http://matw.me/wp-content/uploads/2018/11/404external.png" alt="" width="597" height="525" />
<p class="p1"><span class="s1">And our console.log would never show, of course.</span></p>
<p class="p1"><span class="s1">That’s all there is to it! I also added a special file to this page, and it is logging a question for you in the console. Please take a look and answer the question in the comments.</span></p>