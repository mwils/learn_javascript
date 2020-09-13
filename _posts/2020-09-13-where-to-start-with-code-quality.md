---
ID: 292
post_title: Where to start with code quality
author: Matthew Wilson
post_excerpt: ""
layout: post
permalink: >
  http://matw.me/index.php/2020/09/13/where-to-start-with-code-quality/
published: true
post_date: 2020-09-13 13:58:17
---
Good quality code is a delight to work with, it is easily modified like clay to perform different actions. It is easy to debug and reason about. It is easy to understand and reads almost like a story.

Sometimes I am asked about best practices and code quality and it is a very difficult thing to explain. Furthermore, it is somewhat subjective. However I think many of the principles I learned during composition and rhetoric 101 apply to programming. Essentially good code doesn't just happen, but it is planned and groomed into good code.

When writing an application or even a feature we have a choice about how we go about it. We could:
1. Have one large function that basically does everything
2. Write and string together functions within one file / controller that does everything
3. Write a class containing the logic needed for the feature and use class instances to perform actions

There is no universal answer to what is the right way. It's going to depend upon the goals of the project and the scale of the feature and app. It takes time and experience to learn what is the best way for a given case and even then it's normally not a clear cut decision. But as the expected size and life expectancy of an app / feature goes up, the more we want the code to be extensible and reusable (really this is always desired).

Writing code in self contained classes goes a long ways towards accomplishing this.

Examples of what happens given change of requirements for an application given the above 3 code choices. Let's say we had a zoo application and we needed a way to feed and water the zoo.

Given the <strong>first </strong>style, with everything in one function we would be tempted to write the code like:
<ul>
 	<li>gets tiger food from the freezer</li>
 	<li>feeds the tigers</li>
 	<li>get bucket</li>
 	<li>fills bucket with water</li>
 	<li>water tigers</li>
 	<li>get lion food from the freezer</li>
 	<li>feed the lions</li>
 	<li>get bucket</li>
 	<li>fill bucket with water</li>
 	<li>water lions</li>
 	<li>.... on and so forth</li>
</ul>
With the first scenario if we added another animal we would likely have to add more lines of code to feed and water the animal.

Now lets look at the <strong>second</strong> style, given we have broken things up into multiple functions, we probably wrote it more like this:

<code>Declare function feedAnimal(animal) {
getFood(animal)
feedAnimal(animal)
}
Declare function waterAnimal(animal) {
getAndFillWaterBucket()
waterAnimal(animal)
}
Declare list animals [lions, tigers, bears, ...]
for each animal in animals {
feedAnimal(animal)
waterAnimal(animal)
}</code>

So with the <strong>second</strong> style, you can see that if we need to add more animals to the zoo, all we have to do is add them to the animal list and they will get fed.

Now let's look at the <strong>third</strong> style.

We would write a class that had basically the same functions from the above and it might look something like this:
ZooKeeper file -
<code>ZooKeeper {
feedAnimal(animal) {
getFood(animal)
feedAnimal(animal)
}
waterAnimal(animal) {
getAndFillWaterBucket()
waterAnimal(animal)
}
</code><code>}</code>

ZooController file -
<code>Declare list animals [lions, tigers, bears, ...]
for each animal in animals {
ZooKeeper.feedAnimal(animal)
ZooKeeper.waterAnimal(animal)
}</code>

In this <strong>third</strong> case adding a new animal is the same as the second, so there is not a ton of advantage in that. But our controller is a bit cleaner and probably easier to read. But our class gives us some flexibility if we need to change our zoo app around more.

Say our zoo expands so much that we now added an aquarium section. In our first case we have to write even more code and its starting to get long, jumbled and difficult to manage. In our second case we probably have to write a second controller and rewrite most of the logic from scratch again. Now this is where our <strong>third</strong> case of writing a class really helps. When we add our aquarium we don't want to water those animal so just adding them to our animal list won't work, but we can write a new controller and use our ZooKeeper class and we already have most of our logic done.
AquariumController file -
<code>Declare list aquariumAnimals [sharks, turtles, eels]
for each animal in aquariumAnimals {
ZooKeeper.feedAnimal(animal)
}</code>

So you see that the first form has an advantage in initial simplicity especially for small apps that will likely not grow. The second style is good for apps that may see limited expansion. And the third for takes a bit longer to write initially, but usually pays off as apps and features grow and change.