---
ID: 354
post_title: 'Node &#8211; throttling actions like outbound request'
author: Matthew Wilson
post_excerpt: ""
layout: post
permalink: >
  http://matw.me/index.php/2020/10/09/node-throttling-actions-like-outbound-request/
published: true
post_date: 2020-10-09 18:30:20
---
Occasionally one may have the requirement to run make a lot of request or perform some other action on a large scale, but without overloading any systems.

An example issue, we need to check the status of 5000 different servers as quickly as possible without overloading the network or the requesting server.

Node gives us the ability to send all these request at once if we wanted. We could do that like:
<pre>// requestURLs is defined somewhere and is an array of 5000 urls
const axios = require('axios');
requestURLs.forEach((url) {
axios.get(url).then(requestHandler).catch(requestHandler);
}); // 5000 request will be sent out almost instantly</pre>
This solution has a major issues, the network and your server probably will have a difficult time processing those 5000 request when they start coming back with responses. The best solution is to throttle the request.

Here is a naive throttling function:
<pre>// requestURLs is defined somewhere and is an array of 5000 urls
const axios = require('axios');
const limit 20;

function throttle() {
  while(limit) {
    limit--;
    let url = requestURLs.pop();
    axios.get(url).then(requestHandler).catch(requestHandler);
  }
}

throttle();</pre>
Well this kind of works, 20 request go out and come back, but the rest of the request never go out. Once our limit is hit, the while loop exists and nothing else happens. How can this be fixed?

We have 2 issues:
1. Our limit never goes back up
2. Our throttle function never gets called again after it exits

Issue 1 is solved by incrementing our limit back up when request are done and issue 2 is solved by invoking throttle again.

Here is the finished result:
<pre>// requestURLs is defined somewhere and is an array of 5000 urls
const axios = require('axios');
const limit 20;

function throttle() {
  while(limit) {
    limit--;
    let url = requestURLs.pop();
    axios.get(url)
      .then(requestHandler)
      .catch(requestHandler)
      .finally(() =&gt; {limit++;}); 
  }
}

setInterval(throttle, 2000); // invoke throttle every 2 seconds</pre>
Now our throttle function gets invoked every 2 seconds and the throttle function will sent out request up to our limit.