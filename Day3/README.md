# Day 3 - 01.11.17

## tl;dr
```
We want to find the core of JS that's really good and build on top of those.... there is a beautiful and elegant core.
```

#### Watched/Read:
 - [The future of ES6 (Jafar Husain) - Full Stack Fest 2016](https://www.youtube.com/watch?v=3pKNRgResq0)


#### Points of interest:
 - I didn't realize there was a community where the newest proposals and standards for JavaScript were discussed as propodals moved through the maturity levels - very rad!

#### Continued Learning
 - [ES Discuss Archive/TC39 Discuss with community](https://esdiscuss.org/)

#### ---- Full Notes -----

#### The future of ES6 (Jafar Husain) - Full Stack Fest 2016

Great browser (for desktop) for ES6 (now called ES2015)

Now going to be releasing a new version of JS every year

These versions don't really matter, as moving forward whatever is ready to be added to the standard based on its maturity stage will be added

ES Feature Maturity stages:
0: Strawman
1: Proposal
2: Draft
3: Candidate
4: Finsihed

Why the versions don't matter as much is because you can start use some of these non-finished features today by using something called babel.

Babel allows you to use bleeding edge features by translating them into JS that works in current browsers.

You can select what stage features you wnat to use and take on teh risk that the feature might change once it gets into the standard.

How can we make async easier?
	A lot of people on the commitee stay up at night thinking about.
	JS is a single theaded programming language.
	Introduced Promises in ES6 to help with async code.
	A Promise is an object that represents a value that you'll eventually get async. Has two callbacks attached, one if it succeeds and the other if it errors.
	Can chain sequential operations as a promise instead of sync code.

Why do sync programming and async code have to look so differently?
	No difference if function returns a value or provides it to you ina  callback
	Why should you ahve to mangle your code just to designate which way data is flowing?
	New feature coming (stage 4): Async functions!

Async Functions
	Probably safe to start using them right away
	All functions that retrun promises and just put awaits in front of them
	While this code looks sync, JS will suspend the execution of this function until each promise resolves and then resume
	We dont have to worry about callbacks and js worries about executing our code after these resolve
	Symmetrical language support for sync and async - big thing in future versions.

Cancel Token (Stage 1)
	Allows for a cancellation of chain async functions to stop resolving
	If we do a cancellation between the async function starting and resolving, async function checks for cancellation and will stop the chain if it has been and throw an error.
	We save a whole network request that we didn't even need to amek because we can just cancel that function now.
	await.CancellToken() --> support cancelling in async function with only one extra line of code

Generator Functions
	Function that returns multiple values and when it's done it will say so
	yield is like allow you to have multiple returns
	Instead of having to return you can return each number as they are requested
	When you call a generator function you get an iterator to call .next()-> get next value and bool for whether more data
	yield is basically building a switch/state machine
	Generators functions are great, but sync --> blocks until it returns the next value

Async Generator Functions (Stage 2)
	Allows you to work with i/o sockets like web sockets in a much more streamlined way
	Just add the await and async keywords to a sync function to get data and it makes it an async for consuming data
	Async iterator would be an iterator of promises --> resolve promise to get value

Symmetrical support for sync and async

What if a stream won't wait?
	Add target API in DOM (addeventlistener/removeeventlistener)
	aync iterator isn't great for that as it's best for when the consumer is in control.
	The web has no standard observable interface

Observable Interface (Stage 1)
	Observer is a batch of three different callbacks
	Cal push you a value, error or a completition message
	Provided the observer with an observable and it calls next/pushes data out to you
	Iterator is for pulling data out
	Producer decides when consumer gets the next value (like setInterval/setTimeout/DOMevents)
	removeeventlistener becomes a cancel token
	Would be nice if all dom events used the same interface so we could think about them the same

	Rx/Bacon JS for observables

What about composition?
	We need to control complexity by taking small elements and compose them together
	Can create a stream that only calls us when a price spikes on a stock
	scan is like filter but gives values for the life time of the stream of data coming in

Transpilation allows JS to move so much more quickly because we don't have the same sort of dependencies on browser makers and users

We want to find the core of JS that's really good and build on top of those.... there is a beautiful and elegant core.

I think elm is a much better language than JS, I'd much rather write in Elm, but we're stuck with JS.






