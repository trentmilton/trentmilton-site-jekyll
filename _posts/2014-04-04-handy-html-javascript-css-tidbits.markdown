---
title: Handy HTML, Javascript & CSS Tidbits
date: 2014-04-04 08:34:32.000000000 +10:00
---
The following are some useful bits and pieces for working with HTML.

### Javascript

##### Parse and access JSON
``` language-javascript
var jsonString = '[{"name": "Bob", "age": 31}, {"name": "Jill", "age": 19}]'
var parsed = JSON.parse(jsonString);
for (var key in parsed){
    var person = parsed[key];
    // Do stuff here...
    // e.g.
    console.log(person.name + ' is ' + person.age);
}
```

##### Draw image to canvas
``` language-javascript
var canvas = document.getElementById('my_canvas');
ctx = canvas.getContext('2d');
ctx.drawImage(...);
```

**drawImage** doco [here](http://docs.webplatform.org/wiki/apis/canvas/CanvasRenderingContext2D/drawImage)

##### Loop forever through array
The following allows you to loop through an array, starting from the beggining once you reach the end.
``` language-javascript
var i = 0; // The index
var arr = ... // An array with elements in it
while (true) {
  // This will reset i to 0 when it reaches the length of the array
  i = (i + 1) % arr.length;
}
```
