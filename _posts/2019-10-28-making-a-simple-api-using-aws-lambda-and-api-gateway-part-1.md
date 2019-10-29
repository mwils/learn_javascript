---
ID: 323
post_title: 'Making a simple API using AWS Lambda and API Gateway &#8211; PART 1'
author: Matthew Wilson
post_excerpt: ""
layout: post
permalink: >
  http://matw.me/index.php/2019/10/28/making-a-simple-api-using-aws-lambda-and-api-gateway-part-1/
published: true
post_date: 2019-10-28 22:33:49
---
Serverless architecture gives us an easy way to stand up an API without having to worry about managing a server. Like most decision, the decision to use serverless comes with a host of pros and cons; experience is here, ultimately the best teacher.
<h4>Let's make a simple API using AWS Lambda and API gateway services</h4>
If you haven't yet, go sign up for a free AWS account. Many of the services have a free tier. You can run this example without any cost.

Let's use the classic pet store API for an example. We will have the following GET endpoints:
/animals-for-adoption - gets a list of all animals that are available
/info/{animal-name} - gets the info for an animal by the animals given name

Lambda's are event driven functions that run on Amazon's infrastructure. They look like any other function in JavaScript. Let's make a simple Lambda function that returns a list of available pets.

In your aws account, go to Lambda, then create function. Then select "Author From Scratch". Enter a name for the function, I used <code>getPetsList.</code> Set NodeJS for the run time and click CREATE FUNCTION.

<img class="alignnone size-full wp-image-331" style="color: var(--color__text); font-family: inherit;" src="http://matw.me/wp-content/uploads/2019/10/createFunction.png" alt="" width="650" height="785" />

In a few seconds you should see the Lambda panel for your new function. AWS has provided an IDE so you can edit your function online.

<img class="alignnone size-full wp-image-332" src="http://matw.me/wp-content/uploads/2019/10/lambIde.png" alt="" width="918" height="493" />

&nbsp;

The Lambda is prepopulated with minimum boilerplate code. Here we can see that this file is actually a Node.js Module and it is "exporting" a function named handler. The handler function returns the response object.
<pre>exports.handler = async (event) =&gt; {
  // TODO implement
  const response = {
    statusCode: 200,
    body: JSON.stringify('Hello from Lambda!'),
  };
  return response;
};</pre>
&nbsp;

Let's go to API gateway panel in AWS and hook this up. Click through till you get to the create API page. Select the following options: REST, New API, Regional and give your API a name. Should look something like:

<img class="alignnone size-full wp-image-333" src="http://matw.me/wp-content/uploads/2019/10/apiGate.png" alt="" width="1007" height="613" />

After clicking the CREATE API, you will now have an API with no endpoints. That's not very useful so let's add our getPetList endpoint. Click the "ACTIONS" button and select "Create Resource" from the drop down list.

<img class="alignnone size-full wp-image-335" src="http://matw.me/wp-content/uploads/2019/10/newResource.png" alt="" width="1704" height="442" />

From here you can create a new resource (endpoint) for your API. Let's create our endpoint "/animals-for-adoption".

Enter "Get Pets" for the Resource name, and "animals-for-adoption" for Resource Path. Click "Create Resource" button and you should now see your path in the resources list. However we still need to add a method; we will add a GET method to /animals-for-adoption. With "animals-for-adoption" selected, click the Actions button again, then "Create Method" then select GET from the list.

After you click the check-box you should see something like:

<img class="alignnone size-full wp-image-338" src="http://matw.me/wp-content/uploads/2019/10/Screen-Shot-2019-10-21-at-8.39.36-PM.png" alt="" width="1137" height="439" />

Since we are using a Lambda for our API backend, select Lambda and enter the name of the Lambda function in the input. Click save and then OK to set up the permissions automatically.

You should now see something like this:

<img class="alignnone size-full wp-image-339" src="http://matw.me/wp-content/uploads/2019/10/Screen-Shot-2019-10-21-at-8.42.58-PM.png" alt="" width="1573" height="571" />

Deployment is the last step. Once again click the "Actions" button. Look for the "Deploy API" option under applications. Clicking it produces a popup dialog:

<img class="alignnone size-full wp-image-340" src="http://matw.me/wp-content/uploads/2019/10/Screen-Shot-2019-10-21-at-8.50.55-PM.png" alt="" width="647" height="423" />

Fill it out like this and then click deploy.

After it deploys you should see an invoke url. In a browser, navigate to that url PLUS the endpoint /animals-for-adoption . You should get a response like:
<pre>{"statusCode":200,"body":"\"Hello from Lambda!\""}</pre>
You will need to update your lambda function to get the list of pets from the API, I will cover that in the next post.