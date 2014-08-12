---
layout: post
title: Handy HTML, Javascript & CSS Tidbits
published: true
categories: []
tags: [tidbits, json, parse, image, canvas, array]
---
The following are some useful bits and pieces for working with HTML.

### Javascript

#### Parse and access JSON

	var jsonString = '[{"name": "Bob", "age": 31}, {"name": "Jill", "age": 19}]'
	var parsed = JSON.parse(jsonString);
	for (var key in parsed){
	    var person = parsed[key];
	    // Do stuff here...
	    // e.g.
	    console.log(person.name + ' is ' + person.age);
	}

#### Draw image to canvas

	var canvas = document.getElementById('my_canvas');
	ctx = canvas.getContext('2d');
	ctx.drawImage(...);


**drawImage** doco [here](http://docs.webplatform.org/wiki/apis/canvas/CanvasRenderingContext2D/drawImage)

#### Loop forever through array

The following allows you to loop through an array, starting from the beggining once you reach the end.

	var i = 0; // The index
	var arr = ... // An array with elements in it
	while (true) {
	  // This will reset i to 0 when it reaches the length of the array
	  i = (i + 1) % arr.length;
	}