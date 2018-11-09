---
ID: 39
post_title: >
  How to Create and Use Basic Objects in
  Javascript
author: Matthew Wilson
post_excerpt: ""
layout: post
permalink: >
  http://matw.me/index.php/2018/11/03/a-load-of-objectionable-content/
published: true
post_date: 2018-11-03 15:35:06
---
Previous posts have covered strings, numbers, and arrays. Arrays can help organize related strings and numbers into a list-like behavior, but finding items in the list can be a bit difficult. Javascript offers one more method to organize data called an “object”.  Objects store and retrieve items using a key - value system. For example, if you had an item located somewhere in a room full of lockers, you might tell someone to go and get me the contents of locker 15. In this example, the key is 15. Another example might be a phone book or encyclopedia (ancient relics of the past), where the key would <span style="font-family: inherit, serif;">be the subject title or person's name and the value is the content.</span>
<h4>Time to break some stuff</h4>
Ok, let's go back to the console to look at this concept first hand. (<span style="color: #000080;"><u><a href="http://matw.me/index.php/2018/10/25/the-beginning/">First post covers opening the console</a></u></span>) Let's create a new object called “bank”. Enter the following into the console <code class="western">var
bank = {}</code>. When you press enter, it will create a new object and store it as a variable named bank. To verify this, you can type bank and hit enter. The console will show you a set of brackets like {}. Now, most banks have accounts, so let's add a few accounts to our bank. Good news, our first customer John just walked in and created a new savings account with $500. So we need to store at least two bits of information about John's bank account, the balance, and the account type. For our bank, we need to store multiple bits of information about each account, the best way to do this is by using an object.

As you just learned, objects can store string and numbers, but they can also hold other objects. With that in mind, let's create a new object called John. But this time instead of creating an empty object, we will create the object with John's account information. Similar to when we created the bank object, we will use the var keyword and a set of brackets, but our brackets this time will not be empty. We will add the object's data inside the brackets and each entry will be delimited by a comma. Each item <span style="font-family: inherit, serif;">entry is a key-value pair with a colon separator. So for John's account it will look like </span><code class="western">var john =
{balance: 500, accountType: "savings"}</code><span style="font-family: inherit, serif;">. There are a few things here I want to point out, as I hope to prevent you from confusion. First, you should notice that the "Keys" balance and accountType are not in quotes; this is because they are the "keys" and in the same way that our object name "John" isn't required to be in quotes, they do not need them either. Now it is OK to add the quotes and </span><code class="western">var john =
{"balance": 500, "accountType": "savings"}</code> <span style="font-family: inherit, serif;">would be perfectly valid. Second, string values need to be in quotes, but numbers do not. So now we have an object called bank and an object called account, but this is not very useful yet because we want John's account to be part of the bank variable.</span>
<h4>Putting it all together</h4>
<img class="size-medium wp-image-68 alignleft" style="color: var(--color__text); font-family: inherit;" src="http://matw.me/wp-content/uploads/2018/11/Screenshot-from-2018-11-03-11-08-07-300x255.png" alt="" width="300" height="255" />Now we need to add John's account to our new bank. With John's account, we added the values during the object creation, but we created the bank as an empty object. Now we can add John's account object to our bank object. There are a few ways to add to <span style="font-family: inherit, serif;">objects, here I will cover "dot notation". Adding a subobject to an outer object looks like outerObject.subObject = "value" keep reading a bit if that is confusing. Hopefully, our bank example will help. We already created our empty bank with </span><code class="western">var
bank = {}</code><span style="font-family: inherit, serif;">, now to</span>

<span style="font-family: inherit, serif;">add John's account to our bank with the key, “johnsAccount” we enter </span><code class="western">bank.johnsAccount
= john</code><span style="font-family: inherit, serif;">. Great, now our bank has a new customer named John and we can access his account info using the same dot notation </span><code class="western">bank.johnsAccount</code> This <span style="font-family: inherit, serif;">will return us John's account details.</span>
<h4>Bonus material</h4>
John just came back in and deposited an extra $100, now we need to update his balance, how can we do this? To update John's account, we can use the dot notation to access his balance and update it. To add $100 we could set it to 600 using <code class="western">bank.johnsAccount.balance
= 600</code>, but we could instead let Javascript do the math. There are a few special operators for add, subtract and other math functions. To add to a variable, we can use the <code class="western">+=</code> operator. This is called the “plus assignment” operator. It's called “assignment” since it does the math and reassigns the variable of the output. If we wanted to add 100 to the balance without using the assignment operator, it would look like this: <code class="western">bank.johnsAccount.balance =
bank.johnsAccount.balance + 100</code>. However, using the assignment operator shortens the statement quite a bit to just <code class="western">bank.johnsAccount.balance += 100</code>. Running this will update the balance by adding $100. There is also the -= assignment operator which works the same way, but of course, subtracts.
<h4>Strange behavior</h4>
<img class="size-medium wp-image-75 alignright" style="color: var(--color__text); font-family: inherit;" src="http://matw.me/wp-content/uploads/2018/11/bankaccount-281x300.png" alt="" width="281" height="300" />There is one strange side effect of changing the bank balance. We updated bank.johnsAccount.balance, but what about our original variable of john? It turns out that it gets updated too. Take a look, type john in the console and hit enter and you will see that john.balance has been updated. This is because bank.johnsAccount wasn't just set to the value of "john", it actually is a reference to the variable john. Updating one changes the other as well.

<img class="size-medium wp-image-77 alignleft" style="color: var(--color__text); font-family: inherit;" src="http://matw.me/wp-content/uploads/2018/11/doesntupdate-300x226.png" alt="" width="300" height="226" />

This is a special feature of objects, this same behavior is not repeated with string or number variables. For example, <code class="western">var
foo = "bar" </code><span style="font-family: inherit, serif;">followed by </span><code class="western">var bax = foo</code> <span style="font-family: inherit, serif;">of course sets bax to the value of foo, which is then the string "bar". You might think that changing foo would also change the value of bax, yet it doesn't.</span>

Can you think of some good uses for objects? Leave me some examples in the comments. Remember to practice what you are reading. When I was first learning, I could read and read, but it only "sunk in" once I practiced it. So go ahead and open up that console.