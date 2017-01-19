# Day 5 - 01.13.17

## tl;dr

#### Watched/Read:
 - [02 Creational Patterns Creational Patterns](https://www.youtube.com/watch?v=LjIWRvOL7aM&index=2&list=PLqEsQbKGIlmrpvQcnidKsVWSCV6vjAHN9)
 - [03 Creational Patterns: Generating Objects with Object create](https://www.youtube.com/watch?v=Y4dtUOOqRWE&index=3&list=PLqEsQbKGIlmrpvQcnidKsVWSCV6vjAHN9)
 - [04 Creational Patterns: The Constructor Pattern](https://www.youtube.com/watch?v=g573UN3tPog&list=PLqEsQbKGIlmrpvQcnidKsVWSCV6vjAHN9&index=4)
 - [03 Code Reuse Patterns (Structural): 01 The Inheritance Pattern](https://www.youtube.com/watch?v=mUJ6TOv2LAM&index=5&list=PLqEsQbKGIlmrpvQcnidKsVWSCV6vjAHN9)
 - [03 Code Reuse Patterns (Structural): 02 Mixins](https://www.youtube.com/watch?v=fTNb4yo3S3c&list=PLqEsQbKGIlmrpvQcnidKsVWSCV6vjAHN9&index=6)
 - [03 Code Reuse Patterns (Structural): 03 Mixins Part 2](https://www.youtube.com/watch?v=MqIXZfqYL50&list=PLqEsQbKGIlmrpvQcnidKsVWSCV6vjAHN9&index=7)

#### Points of interest:
 - Getting more into the mechanics of the language and design patterns was a nice change of pace from the future looking conference talks I've been watching this week.
 
#### Continued Learning
- [JSON Linter](jsonlint.com)


#### ---- Full Notes -----

#### Design Patterns in JavaScript

##### 02 Creational Patterns Creational Patterns

Object Literal --> Pair of curly braces
	Can also do new Object(), but more verbose than needed

You can set properties via dot or bracket notation, but bracket notation gives slightly more flexibiliity

Object.defineProperty()
	Good for read-only or properties with getters/setters.
	Example:
	```
	Object.defineProperty(obj, "country", {
		value : "USA"
	})

	```

##### 03 Creational Patterns: Generating Objects with Object create

Technically JS does not have methods, it has properties that contain a function obj

You can use other objects as blueprints for creating new objs with Object.create()

Example:

```
var johnDoe = {
	firstName: "John",
	lastName: "Doe",
	sayName: function() {
		return "This is my name " this.firstName + " " + this.lastName;
	}
}

var janeDoe = Object.create(johnDoe, {
	firstName: {value: "Jane"}
	greet: {
		value: function(person) {
			return "Hello, " + person.firstName;
		}
	}
});

```

##### 04 Creational Patterns: The Constructor Pattern

Constructor functions start with uppercase letter to distinguish from other functions

Using the Constructor patter:
```
function Person(firstName, lastName) {
	this.firstName = firstName;
	this.lastName = lastName;
	this.sayName = function() {
		return "This is my name " this.firstName + " " + this.lastName;
	}
}


var johnDoe = new Person("John", "Doe");
var janeDoe = new Person("Jane", "Doe");

johnDoe instanceOf Person // true

// each method is a newly created function
// results in increased memory usage
johnDoe.sayName === janeDoe.sayName // false


// reworking to add function to prototype

function Person(firstName, lastName) {
	this.firstName = firstName;
	this.lastName = lastName;
	
}

// this is now shared between all the instances of the constructore function
Person.prototype.sayName = function() {
	return "This is my name " this.firstName + " " + this.lastName;
}


var johnDoe = new Person("John", "Doe");
var janeDoe = new Person("Jane", "Doe");

johnDoe.sayName === janeDoe.sayName // true

```

##### 03 Code Reuse Patterns (Structural): 01 The Inheritance Pattern

One of the big goals of OOP is reusability of code

JS does not have classes (I think ES6 does?), it does inheritance through objs inheriting other objs

True inheritance in JS is through chain prototypes

Example: Coffee inheriting from Beverage
```
function Beverage(name, temperature) {
	this.name = name;
	this.temperature = temperature;
}

Beverage.prototype.drink = function(){
	console.log("I am drinking " + this.name);
}

function Coffee(type) {
	// this set-up is odd compared to other OOP languages
	Beverage.call(this, "coffee", "hot")
	this.type;
}

Coffee.prototype = Object.create(Beverage.prototype);

Coffee.prototype.sip = function(){
	console.log("Sipping some awesome " + this.type + " " + this.name);
}
```
The above is inheritance or extending one obj with another

##### 03 Code Reuse Patterns (Structural): 02 Mixins

JS is a prototypial language, not Class based

For performance reasons, you don't want a huge prototype chain as that weighs on the js engine

jQuery extend method adds functionality to a target object (mixins)

Mixins allow us to define functionality to add to different objects without having to create a long prototype inheritance structure

Making the extend function:
```
function extend(target) {
	// if nothing to add to target, return
	if(!arguments[1]) {
		return;
	}

	// add the prop arguments to the target
	for(var ii = 1, ll = arguments.length; ii < ll; ii++) {
		var source = arguments[ii]

		for(var prop in source) {
			// if the target does not have this prop already
			// don't inherit from proto
			if(!tagret[prop] && source.hasOwnProperty(prop)) {
				target[prop] = source[prop]
			}
		}
	}
}

```

Document your mixins, experially in large code bases can get confusing
