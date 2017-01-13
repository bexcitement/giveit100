# Day 4 - 01.12.17

## tl;dr

#### Watched:
 - [Advanced JS performance with V8 and Web Assembly (Chrome Dev Summit 2016)](https://www.youtube.com/watch?v=PvZdTZ1Nl5o)


#### Points of interest:
 - Folks are really excited about async... await - this is the third video in 4 days I've watched of conference talks that touch upon it. It's interesting to see what problems these new parts of the language are looking to solve as it helps guide what pain points I should be learning more deeply.
 - As exciting as it is to learn about all these new and upcoming features of JavaScript, I'm going to try to find material for teh next few days that speaks more to current state rather than future state.
 
#### Continued Learning
- [Angry Bots Game Showing off Web Assembly](webassembly.org)


#### ---- Full Notes -----

#### Advanced JS performance with V8 and Web Assembly

What is V8?
	It's an engine that's part of chrome that runs js
	Make js fast that's already on the web and making it easier to write js
	To do testing for the speed of V8 do testing against a variety of different sites
	Measure the performance of V8 against real web pages
	When we're getting closer and closer to your optimal bench marker, the constraints used for testing become more import - can't just used microbanchmarks

What takes up the most for load time?
	A lot of websites take a portion of the run time to compile js
	Taking a look at these real world benchmark helped make real improvements to page load times
	Lots of speed improvement came from parser and run time - not necessarily in run time compiler

Memory comsumption of V8
	Matters a lot with low memory devices (512MB)
	Made big improvements to memory consumptions by changing heap size and zone memory

Optimizing compiler, baseline compiler
	Hard at work adding an interpreter to V8, which is beneficial because it has a lower memory footprint
	Easier to make improvements with the interpreter

Many js devs are actually full stack devs and front end js is only half the js you care about

Async await!
	Bring readability, debuggablity and ease of writing to async code
	fetch is an api that returns a promise
	await is a keyword that waits for a promise to resolve before the statement ends but it doesn't block the thread/js's event loop
	use the async keyword the dictate that a function is going to ahve awaits inside of it
	If you're using promises at all, updating to use async/await is good to look at

Web Assembly
	Makes it easy to run native code in the web
	Designed to run native C/C++ code in a tiny binary format(very small over the wire).
	Cross browser
	Unlock a new class of high performance apps and computing in teh browser
	Just use a web assembly module to offload intense commuting processes




