---
ID: 299
post_title: >
  Using JavaScript to manipulate a webpage
  using tag names
author: Matthew Wilson
post_excerpt: ""
layout: post
permalink: >
  http://matw.me/index.php/2019/10/05/using-javascript-to-manipulate-a-webpage-using-tag-names-getelementsbytagname/
published: true
post_date: 2019-10-05 11:18:33
---
This is a continuation on previous posts, <a href="http://matw.me/index.php/2019/01/23/using-javascript-to-select-html-elements/">Using JavaScript to Select HTML Elements,</a> &amp; <a href="http://matw.me/index.php/2018/12/01/how-to-use-javascript-to-interact-with-html-webpage/">How to use JavaScript to Interact With HTML Webpage.</a> This will cover selecting HTML elements by tag names.

As a website loads, nodes (sections) of the page get loaded into the <code><a href="https://www.geeksforgeeks.org/dom-document-object-model/">document</a></code> object. The document object has methods that can be used to select, and manipulate the HTML page. Say we want to get all &lt;p&gt; tags on a website and add a smiley face to the end of each, how can we do that? The document's method <code>getElementsByTagName</code> can fetch every &lt;p&gt; tag in a site and then we can modify each P element.

Let's give this a try right now! Right click anywhere on this text (from a desktop / laptop) and then click <strong>Inspect</strong> from the popup menu. You should see a new window open somewhere. Inside this new window, open the console tab <a href="http://matw.me/index.php/2018/10/25/the-beginning/">(See more instructions here)</a>. You can now run JavaScript code inside this console tab. In the blank area, to the left of the &gt;, type or copy the following and then enter: <code>document.getElementsByTagName('p').length</code> You should see a number. That number is the total of &lt;p&gt; element on the webpage.

So back to adding a smiley face to the end of each paragraph.
Instead of jumping straight in, let's do this gradually. Start by console.log each p tag:

<code>allPTags = document.getElementsByTagName('p');
for (pTag of allPTags) {
console.log(pTag);
}
</code>
Now the output should look something like:

<img class="alignnone size-full wp-image-302" src="http://matw.me/wp-content/uploads/2019/10/Screen-Shot-2019-10-04-at-7.53.47-PM.png" alt="" width="389" height="150" />

This is a list of all the &lt;p&gt; tags on the page. Now instead of console.log each of them, we can append (add) to them. We want to add a smiley face. Taking the same for loop and update it a little:

<code>allPTags = document.getElementsByTagName('p'); // Gets all our p tags
for (let pTag of allPTags) { // Loops through each p tag
pTag.append(' :) '); // Add :) to each P tag
}</code>

Go ahead and try it, it's pretty funny. To undo it, just reload your page.

Next post will cover using a button to run the above code.

<a href="https://www.theblogstarter.com/html-for-beginners/#ftoc-heading-1">Need to learn more about HTML? Here is a good resource.</a>