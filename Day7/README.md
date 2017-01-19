# Day 7 - 01.18.17

## tl;dr

#### Watched/Read:
 - [Web APIs you [probably] didn’t know existed... with Zeno Rocha](https://www.youtube.com/watch?v=NCGLPp778JY)
 - [Essential JS Design Patterns](https://addyosmani.com/resources/essentialjsdesignpatterns/book/)

#### Points of interest:
 - 
 
#### Continued Learning
- [Page Visbility API](https://developer.mozilla.org/en-US/docs/Web/API/Page_Visibility_API)
- [Network Information API](https://developer.mozilla.org/en-US/docs/Web/API/Network_Information_API)
- [Online and Offline Events](https://developer.mozilla.org/en-US/docs/Online_and_offline_events)
- [ZeroClip Board](zeroclipboard.org)
- [Clipboard.js](clipboardjs.com)
- [Generic Sensor API](https://www.w3.org/TR/2016/WD-generic-sensor-20160830/)

#### ---- Full Notes -----

##### Web APIs you [probably] didn’t know existed... with Zeno Rocha

2008: HTML5 arrives! It was great - Flash is going to die.

2014: HTML5 spec was presented as a recco which is the final step for W3C to approve - which means it's ready.

Lots of good/bad reviews along the way all while folks are building HTML5 games 

Going to show some lesser known web apis that are useful

Page visibility
	Provides as API to check whether the current page is visible or not

```
window.addEventListener('visibilitychange', function(){
	if(document.hidden) {
		console.log('Tab is hidden')
	}
	else {
		console.log('Tab is focused')
	}	
})

```

new states to check for with new method
```
window.addEventListener('visibilitychange', function(){
	switch(document.visibilityState) {
		case 'prerender':
			console.log('Tab is pre-rendering')
			break;
		case 'hidden':
			console.log('Tab is hidden')
			break;
		case 'visible':
			console.log('Tab is focused')
			break;

	}	
})


```

	Useful if you're playing a video to have it start and stop based on whether someone is actually viewing the webpage the video is on.

Online State
	Exposes network connection availability information to the web.

	Identify from a webpage whether some is on or offline.

```
window.addEventListener('offline', networkStatus)
window.addEventListener('online', networkStatus)

function networkStatus(e){
	console.log(e.type)
}

```

Solid browser support for online state and page visibility 

Network Information API
	What is the download speed for the user?
	Can give user feedback if the network connection goes away - like a butter bar pop up when the go offline

Vibration
	Provides access to a form of tactile feedback.

Super Mario Bros theme:
```
navigator.vibrate([125,75,125,275,200,275,125,75,125,275,200,600,200,600])
```

	Only really works on mobile, won't do anything on desktop.

	This works on some browsers but is getting progressive support.

	Good for a game or form validation.

Device orientation

```
let logo = document.querySelector('img');

window.addEventListener('deviceorientation', function(e) {
	let tiltLR = e.gamma;
	let tileFB = e.beta;

	....
}

```

	Can use css transform property to mve the image based on how a phone is rotated

	Can look around a picture based on how you rotate your phone.

Clipboard
	Standard API for interacting with the clipboard (copy/paste/cut)

	Zeroclipboard is a widely used library to solve for this problem, but requires Flash :(

User interaction is required to use these functions, can not simulate events
```
let button = document.querySelector('button');

button.addEventListener('click', function(){
	select();
	copy();
})
```
	This API is a bit difficult to just do something simple, so created clipboard.js

	Clipboard.js works on everything on Safari

Ambient Light
	Exposes the sensor data that captures the light intensity.

```
window.addEventListener('devicelight', (e) => {
	console.log('${e.value] lux')
})


```

	Works on desktop too - can sense lighting and change functionality of your app.

	Doesn't have a ton of support yet, but getting better as the API gets finalized.

	Good use cases for better contrast when a user goes outdoors.

Battery Status
	Allows a webpage to access battery information from desktop and mobile devices.

	Know whether charger is on/off and how much battery you have left.

	Promise based API. Lots of events you can get back.

```
navigator.getBattery().then(function(battery){
	console.log(battery.level)

	battery.addEventListener('levelchange', function(){
		console.log(this.level)
	})
})


```

More Future looking:

Web Assembly
	Low level programming language for the web
	Designed for running complex code in the browser with good performance
	Great for VR

Gamepad
	Access game controller via usb and check how many controllers and what type.

	Has good browser support.

