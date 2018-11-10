---
ID: 6
post_title: >
  How to Use Chrome DevTools and the
  Console Tab to Learn Javascript
  Programming
author: Matthew Wilson
post_excerpt: ""
layout: post
permalink: >
  http://matw.me/index.php/2018/10/25/the-beginning/
published: true
post_date: 2018-10-25 21:27:08
---
<h4>This post will show you how to open and use Chrome devTools on a desktop or laptop computer</h4>
The console and inspector were essential to me as a beginning developer and after 10 years experience I still use it almost daily.

First step (using Chrome) <strong>right click on your screen</strong>. Anywhere within the browser should work. A dialog menu box should appear.

<img class="alignnone wp-image-10 size-full" title="Menu box" src="http://matw.me/wp-content/uploads/2018/10/menu.png" alt="right click menu" width="361" height="338" />

<strong>Click the "Inspect" button</strong> to open Chrome devTools.

<img class="alignnone size-full wp-image-126" src="http://matw.me/wp-content/uploads/2018/10/inspector-lg-2.png" alt="" width="1246" height="537" />

The inspector has multiple tabs, we are interested in the <strong>"Console" tab</strong>.

After clicking on the Console tab, you may see some text, errors, or other messages. Some websites even have hidden Easter eggs in the console. The important bit is that you can execute Javascript code here. For example, click just to the right of the &gt; sign and enter 2+2, followed by enter. This should output the correct answer of 4. You can also do subtraction, multiplication 5*5, division 10/5, and a special one called modulus which gives you the remainder after a division operation. For example, 10%2 would equal 0, since there is no remainder, but 10%3 will return 1, since the “remainder” of 10 divided by 3 is 1.

&nbsp;
<h4>The weird parts</h4>
So you saw how you can use the console tab as a calculator, but there are some strange things that can happen here. Check this out, add 0.1 and 0.2. Now I'm sure you can do this in your head, but go ahead and enter it into the console <code class="western">0.1 + 0.2</code>. You would expect the result 0.3, but it actually outputs something like 0.30000000000000004. Strange, isn't it? This happens because Javascript uses floating point math. In short, it cannot accurately store nonintegers like 0.1. The math is close, but not exact.
<h4>Other Resources</h4>
They are a ton of great resources online to help get you started on your learning path.

Check out " <a href="http://javascriptissexy.com/how-to-learn-javascript-properly/">How to Learn JavaScript Properly</a>" for encouragement and ideas for learning with others.

Also check out <a href="https://blog.alexdevero.com/6-quick-proven-tips-learn-javascript/">Alex Devero's</a> blog for learning and study tips.

Do you know any other weird parts of Javascript? If so, tell about them in the comments.