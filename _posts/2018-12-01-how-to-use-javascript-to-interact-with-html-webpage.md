---
ID: 181
post_title: >
  How to use Javascript to Interact With
  HTML Webpage
author: Matthew Wilson
post_excerpt: ""
layout: post
permalink: >
  http://matw.me/index.php/2018/12/01/how-to-use-javascript-to-interact-with-html-webpage/
published: true
post_date: 2018-12-01 20:32:01
---
<p class="p1"><span class="s1">One of the most useful aspects of JavaScript is its ability to manipulate a website. When a pure HTML website loads, that's it—it's done and it will not change again until the page is reloaded. Adding JavaScript to a page, however, gives us the ability to update a page even after it has been completely loaded. We’re going to be using the Chrome devTool's console for this post, so if you don't know how to open it and use it, please check out the <a href="http://matw.me/index.php/2018/10/25/the-beginning/">console post</a> for more info.</span></p>

<h4>The HTML Document</h4>
<code></code>
<p class="p1"><span class="s1">The HTML document is composed of elements that are created using tags. HTML tags have the standard format </span><code>&lt;tagname&gt;Content&lt;/tagname&gt;</code></p>
<p class="p1"><span class="s1">, and they describe the type of content they contain. For example, to indicate the beginning and end of a paragraph, the content is wrapped using a “p” tag: </span><code></code><code>&lt;p&gt;The paragraph goes here.&lt;/p&gt;</code>. W3 School<a href="https://www.w3schools.com/html/html_elements.asp"> has a great in-depth article here</a> covering HTML tags.</p>
<p class="p1"><span class="s1">When using JavaScript to manipulate an HTML document, we can use the tags as a road map to navigate and select the document section we want to manipulate.</span></p>

<h4>What is the DOM</h4>
<p class="p1"><span class="s1">When dealing with JavaScript and HTML you will likely hear people refer to the DOM. DOM stands for Document Object Model, and it is essentially an interface that allows JavaScript to access the web page "document."</span></p>
<p class="p1"><span class="s1">To illustrate this point, imagine a string puppet for a minute. If you think of a web page as a puppet, then the DOM could be thought of as the strings and the points at which they attach to the puppet.</span></p>
<a href="http://www.puppetsinprague.eu/instructions/stringing_puppet/knee.jpg"><img class="alignnone size-full wp-image-186" src="http://matw.me/wp-content/uploads/2018/11/knee.jpg" alt="" width="280" height="373" /></a>
<p class="p1"><span class="s1">Using this same analogy, JavaScript would best be compared to the stick that controls the strings. The DOM allows us to connect JavaScript and HTML together.</span></p>
<img class="alignnone size-medium wp-image-185" src="http://matw.me/wp-content/uploads/2018/11/p7-185x300.jpg" alt="" width="185" height="300" />
<p class="p1"><span class="s1">Included with a browser's JavaScript version is an object called the "document." It is on this object that we can find methods that allow us to interact and manipulate the DOM. Continuing with the analogy, the puppet control sticks have multiple "methods" or actions that can be used to manipulate the puppet.</span></p>
<p class="p1"><span class="s1">The DOM is made up of elements that are connected in a tree-like structure. The elements of this tree are objects, and they can be accessed from the root document object mentioned in the previous paragraph.</span></p>

<h4>Navigating the DOM</h4>
<p class="p1"><span class="s1">Before we can manipulate a section of the DOM, we first need to know how to select an element. To help with this, I’ve made a very simple web page that you can experiment with: <a href="http://matw.me/example.html">http://matw.me/example.html</a>. Open this page in a new tab and follow along.</span></p>
<p class="p1"><span class="s1">Here is what the HTML code of this example.html page looks like:</span></p>

<pre>&lt;!DOCTYPE html&gt;
&lt;html&gt;

  &lt;head&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;div&gt;
      &lt;h1&gt;Div 1 Heading 1&lt;/h1&gt;
      &lt;p&gt;Paragraph 1&lt;/p&gt;
      &lt;p&gt;Paragraph 2&lt;/p&gt;
    &lt;/div&gt;
    &lt;div&gt;
      &lt;p&gt;Div 2 Paragraph 3&lt;/p&gt;
      &lt;span&gt;
        Text inside span 1.
        &lt;span style="color: blue;"&gt;I am a span within a span.&lt;/span&gt;
      &lt;/span&gt;
    &lt;/div&gt;
  &lt;/body&gt;
&lt;/html&gt;
</pre>
<p class="p1"><span class="s1">As you can see, it's a fairly simple page. There is an inline style to color the nested span blue, but not much else is going on. First off, let’s change the text of the first paragraph.</span></p>
<p class="p2"><span class="s1">Before we can manipulate the first paragraph, we have to select it. There are many ways to select an element on a page—you can get elements by class name, id, tag name, or by "walking" up and down the DOM tree. Since the "document" is the DOM root, everything on the web page is a child of the document. </span></p>
<p class="p1"><span class="s1">This may be a bit difficult to understand, so let's take a closer look at it. Go to the <a href="http://matw.me/example.html">example.html</a> page and then open the console. Then type in document.children and press enter. The console should look something like:</span></p>
<img class="size-full wp-image-192 alignnone" src="http://matw.me/wp-content/uploads/2018/11/Screen-Shot-2018-11-21-at-8.12.28-PM.png" alt="" width="203" height="63" />
<p class="p1"><span class="s1">Now click the triangle to expand the HTMLCollection object. Can you see how it compares to our HTML code? The first and only child element is the "html" object. This is the root from which everything else on the page stems. Since this is an object, we can save it to a variable. To do that, use</span> <code>var htmlRoot = document.children[0]</code> <span class="s1">and press enter. We have to add </span><code style="color: var(--color__text);">[0]</code> <span class="s1">to the end of our document.children because we want the first child. In JavaScript, the first item is item 0. Now our variable htmlRoot is a reference to the DOM's html object. Looking back at our page code, you can visualize what this variable references on the page.</span></p>
Let's take a look at the HTML's hierarchical structure:
<img class="alignnone size-full wp-image-195" src="http://matw.me/wp-content/uploads/2018/11/Screen-Shot-2018-11-21-at-8.31.38-PM.png" alt="" width="658" height="394" />
<p class="p1"><span class="s1">In the console, we can view the content of our htmlRoot variable. Enter <code>htmlRoot</code> and you should see:</span></p>

<img class="alignnone size-full wp-image-204" src="http://matw.me/wp-content/uploads/2018/11/Screen-Shot-2018-11-22-at-10.04.55-AM.png" alt="" width="290" height="185" />

In a tree form, this would look like:
<img class="alignnone size-full wp-image-203" src="http://matw.me/wp-content/uploads/2018/11/dom-tree.png" alt="" width="246" height="205" />
<p class="p1"><span class="s1">As you can see in the tree above, "html" has two children: "body" and "head." If we want to navigate to the first paragraph, we have to go through the "body" and then the first "div." The first paragraph will then be the second child.</span></p>
<p class="p1"><span class="s1">Let’s return to navigating to our first paragraph element, and take it one step at a time. Remember the htmlRoot object we created earlier? This is the html element at the top of our tree, so if we enter <code>htmlRoot.children</code>, we should see that htmlRoot has two children: “head” and “body.”</span></p>

<img class="alignnone size-full wp-image-205" src="http://matw.me/wp-content/uploads/2018/11/Screen-Shot-2018-11-22-at-10.07.34-AM.png" alt="" width="264" height="68" />
<p class="p1"><span class="s1">We already know we want the body, which is the second child. Since our index starts at 0, <code>htmlRoot.children[0]</code> would refer to the head, and <code>htmlRoot.children[1]</code> would refer to the body. Let's save the body as a new variable. We can do that with <code>var body = htmlRoot.children[1]</code>, and pressing enter.</span></p>
Now let's look at our body variable:
<img class="alignnone size-full wp-image-206" src="http://matw.me/wp-content/uploads/2018/11/Screen-Shot-2018-11-22-at-10.13.58-AM.png" alt="" width="371" height="258" />

<em>All the code entered to get here is recapped at the bottom of the page.</em>
<p class="p1"><span class="s1">Well, I think that's pretty neat. We now have a JavaScript variable that represents the HTML "body" element. Now to get that first paragraph, we need to go to the first child of the body, which is a “div” and then the second child of that div would be our paragraph (p element). That will be:</span></p>

<pre>var firstDiv = body.children[0]
var firstParagraph = firstDiv.children[1]</pre>
In the console it would look like:
<img class="alignnone size-full wp-image-208" src="http://matw.me/wp-content/uploads/2018/11/Screen-Shot-2018-11-22-at-10.21.58-AM.png" alt="" width="351" height="153" />
<p class="p1"><span class="s1">As you can see, we finally have our paragraph saved as a variable! Now we can manipulate the text, style, class, id, or other attributes of our “p” element. This style of selecting an HTML element by going up or down the tree using children or parent selectors is called "walking the DOM." There are other ways to select elements on a page, but I will cover these in future posts.</span></p>

<h4>Changing An Element's Text With JavaScript</h4>
<p class="p1"><span class="s1">Let's update the text in our first paragraph to say "Hello World." Even though navigating the DOM and selecting the first paragraph was somewhat complicated, changing the text itself is very easy. The paragraph element, which is of course an object, has a property "innerText." If we type <code>firstParagraph.innerText</code>, we will see the current text of the element returned.</span></p>
<img class="alignnone size-full wp-image-211" src="http://matw.me/wp-content/uploads/2018/11/Screen-Shot-2018-11-22-at-8.30.22-PM.png" alt="" width="350" height="87" />
<p class="p1"><span class="s1">We can simply set this innerText to our new value and it will update the page.</span></p>

<code>firstParagraph.innerText = "Hello World"
</code>
<p class="p1"><span class="s1">Instantly, our text gets updated to "Hello World".</span></p>

<h4>Recap</h4>
<p class="p1"><span class="s1">In order to update a section of text on the screen, the first step we need to take is selecting the element's DOM object. Then we can reassign the inner text. For this page, it looks like:</span></p>
<img class="alignnone size-full wp-image-212" src="http://matw.me/wp-content/uploads/2018/11/Screen-Shot-2018-11-22-at-8.44.44-PM.png" alt="" width="992" height="466" />
<h4>What's next?</h4>
<p class="p1"><span class="s1">There are lots of methods that can be used to select elements from the DOM, and while many of them would have made selecting this element easier, in my opinion it is very important to learn how to navigate the DOM using a simple straight “walk down” as demonstrated here. Learning this method helps provide an understanding of what the DOM is and how it is structured.</span></p>
<p class="p1"><span class="s1">In my next post, I plan to go over other "document" methods that will make navigating and manipulating the DOM simpler and faster.</span></p>
<p class="p1"><span class="s1">In the meantime, play around with selecting DOM elements and updating them. Share some screenshots in the comments section.</span></p>
&nbsp;