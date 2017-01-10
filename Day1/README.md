# Day 1 - 01.09.17

## tl;dr
```
"My biggest professional development was getting comfortable admitting what I don't know" #juniordevforlife
```

#### Watched:
 - [Anjana Vakil: Learning Functional Programming with JavaScript - JSUnconf 2016](https://www.youtube.com/watch?v=e-5obm1G_FY&index=8&list=PLUS3uVC08ZapyqfU21joP-B1vTItKf5qi)
 - [The myth of the “Real JavaScript Developer” – Brenna O'Brien / Front-Trends 2016](https://www.youtube.com/watch?v=Xt5qpbiqw2g&list=PLUS3uVC08ZapyqfU21joP-B1vTItKf5qi)
 - ["Real JavaScript Developer" Slides](http://talks.brennaobrien.com/real-developer/myth-of-the-real-javascript-developer.pdf)

#### Points of interest:
 - Structural sharing (represent data as a tree, replace leaf node as they are updated) in functional programming is an interesting approach for memory management within functional programming. Addresses some of the issues of how do we not create a zillion copies of an array to ensure we're not having side effects?
 - Functional programming is helpful if one of the things you need to optimize for is not having unexpected data mutations. Functional programming seeks to have no "side effects" ie. only uses and returns what was inputted in a given function. I want to dig into this further to explore systems where functional programming as a paradigm is the strongest option and how that is implemented.
 - An excellent pictoral representation of map/reduce:
![alt tag](http://api.ning.com/files/-3i3rVffQH2bautHoYhtuyn-BhEFBMR3TNXJzACS9ATLysgH7VID6G3-DRqv65rcjsIwZ7riHJZ9rtS9XGWzIc326dpaeNvF/bor55.PNG)
 - Breanna O'Brien was exactly what I needed as I was kicking off this adventure. Her perspective on the over-dealized Front-end developer rockstar was refreshing. Her break down what she views as the true markers of a great developer(Resourceful, Excepting, Creative) reminded me again that being a great engineer is so much more than being able to write code for 12 hours a day.
 - Also, the front end spectrum is intense, awesome and makes me a bit nauseous:
![alt tag](https://cdn-images-1.medium.com/max/2000/1*bbxDiplpyPrwg-g7GXC-FA.png) 
 
#### Continued Learning
- [Immutable Structures in JavaScript](http://jlongster.com/Using-Immutable-Data-Structures-in-JavaScript)
- [Introduction to function programming - Mary Rose Cook](https://codewords.recurse.com/issues/one/an-introduction-to-functional-programming)
- [The Front End Spectrum (whoa)](https://medium.com/@withinsight1/the-front-end-spectrum-c0f30998c9f0#.8ps8klkn6)

#### ---- Full Notes -----

#### Anjana Vakil: Learning Functional Programming with JavaScript

Learned functional programming within JS in the last 6 months - her talk will be taking us through her learning journey.

###### What is functional programming?
A programming paradigm (Other examples: Object Oriented)
Functions are King
Style of organizing your code
Mindset - way of thinking about a problem

###### Why do functional programming in JS?
OO was very confusing coming from other languages (What is the this keyword??)
Functional felt easier to debug and maintain
Already a community built around functional programming

###### How do we do it?
Express everything in our program in functions
In FP, we want to approach a problem as "what is the flow of data?" Versus what are our obj and how do they interact
Taking inputs and return values
Express how inputs are manipulated to return outputs

###### Avoid side effect/create pure functions
Side effects: Anything a function might do that effects the global space
Pure: Commuting it's output based on your inputs and returning that output
 - Take an input, only use that and return output

Not pure:
```
var name = "Becca";

function greet() {
console.log("hai! My name is " + name);
}
```

Pure:
```
function greet(name) {
return "hai! My name is " + name;
}
```

###### Higher order functions
Treating functions as objects
Functions that can take other functions as params or return other functions
Don't iterate!
Instead fo using for loops, Use higher order functions like map/filter/reduce instead

##### What is map reduce?
Let's make a sandwich with map/reduce! http://www.datasciencecentral.com/forum/topics/what-is-map-reduce

Map: Give the function a list of ingredients with the function chop and get a list of chopped ingredients back

Reduce: With list of chopped ingredients, combines all the items in a list in certain way

Filter: Filter out ingredients you hate, only items that aren't pickles get through

With these higher order functions, you don't mutate data - don't change data in place.

Changing data in place is something functional programming avoids, which can cause unexpected bugs.

Data mutation:
```
var rooms = ["H1, "H2", "H4"]

rooms[2] = "H3"

console.log(rooms) 
// ["H1, "H2", "H3"] 
```
Functional Approach - no data mutation!
```
var rooms = ["H1, "H2", "H4"]

var newRooms = rooms.map(function(rm){
	if(rm=="H4") { return "H3"}
	else{return rm}
})
console.log(rooms) 
// ["H1, "H2", "H4"] 

console.log(newRooms) 
// ["H1, "H2", "H3"] 
```

###### Persistent Data Structures
Phil Bagwell: Ideal hash trees
 - The idea for persistent data structures came from this paper
 
Rich Hickey: Invented Clojure
 - Invented Clojure to make it very effecient for these persistent data structures

Represent data as a tree - structural sharing
 - Instead of copying over a whole new array to only change one element, instead create a new tree that uses the leaf noes you want and creates new leafs for the new elements
 - Share the data you want and only create the net new information

Libraries that take advantage of structural sharing:
 - Mori - use Clojure script
 - Immutable.js - FB developed


###### Ready to try it out?
Functional Programming libraries:
 - Underscore
 - Lodash
 - Ramda

Mary Rose Cook - Intro to Functional Programming (great blog post): https://codewords.recurse.com/issues/one/an-introduction-to-functional-programming

Q: Is functional or OOP better?
A: Each paradigm has it's advantages or disadvantages based on the problem you're trying to solve and what gets most complex in terms of maintainablilty.

#### The myth of the “Real JavaScript Developer” – Brenna O'Brien

We've so built up in our culture what it means to be a real developer and successful, but you don't need to be that to be a good dev who gets the job done.

The front-end spectrum (whoa): https://medium.com/@withinsight1/the-front-end-spectrum-c0f30998c9f0#.8ps8klkn6

Can feel very overwhelming feeling like you need to keep up with everything.
It's ok to not know everything, a lot of these are competing tools, it's ok to find your niche.
Stop tool and technique shaming!
Use something new and shining only when it actually solves a problem, not just because it's the newest, coolest thing.
Need to stop this feeling that we need memorize everything.

"They had wasted their time memorizing stuff that I could look up in 15 minutes" - Richard Feyman
Trivia on syntax and how a programming language works, does not make a successful dev - you can look all of this up.
Programming is not a test!
Any memorization I have done has come out of repeated use
Instead of memorizing everything, real devs use resources wisely
"If you want them to RTFM, make a better FM"

Your peers are a resource!
Requires you to be vunerable
"My biggest professional development was getting comfortable admitting what I don't know" - Jessica Rose
Just because you don't know one slice of the pie, doesn't negate the slice of the pie you know
Journey as developers are just continually learning, it's never done #juniordevforlife
Lesson: Real devs accept the unknown and accept they can not know everything

You ahve unlimited re-tries -- you don't need to measure twice and cut once, you ahve unlimited retries
Failure isn't really detrimental along the way, it's like a video game - you just get another life to try again
"I have not failed, I've just found 10,000 ways that don't work." - Edison, inventing the light bulb
Failing is just as important as the building blocks of the language
Lessons: Real devs know how to debug and fail successfully

Show you work - warts and all
The "Well Actually" fear of putting out your code and someone immediately finds something to nit pick about rather than celebrating the successes
Celebrate small wins with praise or a high five - helps the whole team.
Lesson: Encourage others.

We need to do things that are not code sometimes to be able complete people and actually solve the problems of the world.
There is totally a place for folks who have that passion, drive and interest to code outside of work, but that shouldn't be the norm.
Being a developer does not have to negate your passions.
Bring your hobbies in with your other hobbies.
Lesson: Think otuside the browser.

Real Devs are:
Resourceful 
Accepting
Creative

slides: http://talks.brennaobrien.com/real-developer/myth-of-the-real-javascript-developer.pdf



