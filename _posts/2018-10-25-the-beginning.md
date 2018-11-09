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
So you have an interest in learning development, but don't know where to start? Here are some first steps to get you started.
<h4>Console</h4>
[caption id="attachment_10" align="alignleft" width="199"]<img class="wp-image-10" src="http://matw.me/wp-content/uploads/2018/10/menu-300x281.png" alt="menu" width="199" height="195" /> Right click menu[/caption]

Let's poke around in your browser. So everybody is on the same page, let's use Chrome web browser for this. OK, right click on your screen. Anywhere within the browser should work. A dialog menu box should have just opened up. The last item should be "Inspect". Click the inspect section to open Chrome devTools. There are a lot of neat things you can do from here. For now, let's look at the Console tab.

After clicking on the Console tab, you may see some text, errors, or other messages. Some websites even have hidden Easter eggs in the console. The important bit here is that you can actually execute Javascript code here. For example, click just to the right of the &gt; sign and enter 2+2, followed by enter. This should output the correct answer of 4. You can also do subtraction, multiplication 5*5, division 10/5, and a special one called modulus which gives you the remainder after a division operation. For example, 10%2 would equal 0, since there is no remainder, but 10%3 will return 1, since the “remainder” of 10 divided by 3 is 1.

<img class="size-medium wp-image-12 alignleft" style="color: var(--color__text); font-family: inherit;" src="http://matw.me/wp-content/uploads/2018/10/inspector-300x172.png" alt="" width="300" height="172" />
<h4>The weird parts</h4>
So you saw how you can use the console tab as a calculator, but there are some strange things that can happen here. Check this out, add 0.1 and 0.2. Now I'm sure you can do this in your head, but go ahead and enter it into the console <code class="western">0.1 + 0.2</code>. You would expect the result 0.3, but it actually outputs something like 0.30000000000000004. Strange, isn't it? This happens because Javascript uses floating point math. In short, it cannot accurately store nonintegers like 0.1. The math is close, but not exact.
<h4>Other Resources</h4>
They are a ton of great resources online to help get you started on your learning path.

Check out " <a href="http://javascriptissexy.com/how-to-learn-javascript-properly/">How to Learn JavaScript Properly</a>" for encouragement and ideas for learning with others.

Also check out <a href="https://blog.alexdevero.com/6-quick-proven-tips-learn-javascript/">Alex Devero's</a> blog for learning and study tips.

Do you know any other weird parts of Javascript? If so, tell about them in the comments.