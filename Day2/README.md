# Day 2 - 01.10.17

## tl;dr
```
In spite of popular beliefs there is no one thing you're destined to do. Purpose doesn't happen to you any more than love does. These things evolve when you commit yourself fully to something, or someone, and make the decision to work through the muck.
from Deliberatism - The Muck, by Eric Karjaluoto
```

#### Watched/Read:
 - [Angelina Fabbro: JavaScript Masterclass | JSConfUS 2013](https://www.youtube.com/watch?v=v0TFmdO4ZP0&index=21&list=PLUS3uVC08ZapyqfU21joP-B1vTItKf5qi)
 - [Slides](http://afabbro.github.io/jsconf2013)
 - [Choosing Vanilla JavaScript in 2016](https://andrewrabon.com/choosing-vanilla-javascript-in-2016-6f38a8302ee5#.bymlo06yv)

#### Points of interest:
 - Multiple days of watching conference talks that discuss the undercurrent of imposter syndrome and what it means to be a "good" developer is a helpful perspective as I'm starting down this adventure.
 - ES6 and the expanding browser support for features natively is exciting. How rad are template strings?

#### Continued Learning
 - [The Best of edw519](http://v25media.s3.amazonaws.com/edw519_mod.html)
 - [Learning Advanced JavaScript](http://ejohn.org/apps/learn/)
 - [JavaScript’s Apply, Call, and Bind Methods are Essential for JavaScript Professionals](http://javascriptissexy.com/javascript-apply-call-and-bind-methods-are-essential-for-javascript-professionals/)
 - [template strings](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/template_strings)
 - [Exploring ES6: Modules by Dr. Axel Rauschmayer](http://exploringjs.com/es6/ch_modules.html)


#### ---- Full Notes -----

#### Angelina Fabbro: JavaScript Masterclass

Trying to become an expert when I'm an intermediate programmer

Lots out there for beginner's to get going, but as an intermediate "I'm writing code, but how do i make it better?" - there is less.

Cognitive biases:
###### You are not special
	motivational anti-pattern
	You think you're special then you don't practice as much
	Or, anyone who is good at something you think is because they are special rather than from practice
	No one is naturally a good programmer

###### You are the result of many complicated interactions
	Things that make you seem like a natural, usually has to do with your early childhood education
	Nebulous to say you have a genetic disposition 
	Big factors are whether you're positively exposed to logically thinking and math

###### Problematic framing of this topic
	Giving a test to incoming students to predict whther they will be good programmers
	Small sample size and only maybe predicts how these people will do in class not whether good programmers

###### Experts are not born with natural talent -- which is actually really empowering!
	Anyone can move toward mastery
	If you practice and code and get some domain knowledge - you too can become an expert!

###### How do I know I'm not a beginner?
	You can use the fundamentals in all languages (control structures, variable assignment)
	You can write code from scratch (without libraries) and not just editing/gluing together (though this is an important step)
	You check out the libraries you use and look under the hood to see how things actually work
	You feel like your code is mediocre but don't know how to talk about it
	Feel a lot of pressure to be really great and learn really fast

###### How do you know you're not an expert?
	You get into that library code, but still don't quite know everything that is going on
	What the heck is the difference between call and apply anyway?
	You can't explain what you know in a patient and clear way
	You aren't confident debugging
	Took a long time to get into the debugger and having a mental model for different debugging strategies
	You rely on references too much - write more code without interruptions if language is more internalized

###### What makes a great programmer?
	[Ed Weissman - Who is a good programmer?](https://edweissman.wordpress.com/2013/03/24/who-is-a-good-programmer/)
	
	Ask why obsessive short of existential angst
	Why did I use jQuery? Why did I use twitter bootstarp?
	
	You should teach or speak at an event!
	There's this idea that if you speak at a conference, you are an expert - not true. You just not a project or a topic that you've gone deep on to share.
	Both are very enlightening, get to formalize and make the ideas about what you've learned more concrete as well as a good moment to reflect on the kind of assumptions you make about your own knowledge. We know much more than we give ourselves credit for!

	Work through a through a suggested curriculum (books)
	[Learning Advanced JavaScript](http://ejohn.org/apps/learn/)
	Going through a book like that will help you re-affirm what you know and don't know.

	Experiment Recklessly(The code does not care)
	No one even sees it until you push it to a branch!

	You should have opinions
	As you get more experienced you'll naturally form opinions about things - express them!
	Being wrong is fantastic as it gives you an opportunity to learn.

	Seek mentorship
	In and out of work.

	Program a lot.

	Stop fucking programming sometimes.
	You need breaks - we can't just program for 24 hours.

	Write JavaScript a lot.

	Write in another language for a while.
	Helps you discover all the interesting nuances of JS and excercises the brain.

	Think like a programmer when AFK.
	Optimize your IKEA route!

	Know what good feedback is and reject all else.
	Sometimes people aren't very happy with themselves and want to take it out on you.

	Break free of imposter syndrome.
	If you write code, you are a developer. The end.

	Fall in love with your process.

#### Choosing Vanilla JavaScript in 2016

Advocating for responsible library use especially with those who heavily use libraries and with all the ES6 additions.

Testing a thought experiemnt to see what of the current dev tooling (jquery, less twig, require.js) could be replaced with vanilla JS.

Using the fetch API instead jQuery ajax methods. Many browsers have support except for IE

Examples:

jquery
```
$.ajax('/user/1')
.done(function (data) {
  var user = data;
});

```

fetch
```
fetch('/user/1')
.then(function (response) {
  return response.json();
})
.then(function (data) {
  var user = data;
});
```

Can use [template strings](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/template_strings) for reusable code blocks
```
var firstName = 'Andrew';
var lastName = 'Wizard';
var fullName = `<div class="full-name">
  <em>${firstName}</em> <strong>${lastName}</strong>
</div>`;
document.querySelector('body').innerHTML = fullName;

```

All browsers have support - but do need to evaluate security concerns.

[Modules](http://exploringjs.com/es6/ch_modules.html) are set to be supported in ES6 and take on either a Require JS or Common JS pattern.

Native CSS variables are a big selling point in pre-processors like Sass and Less. They exist natively in many browsers now.




