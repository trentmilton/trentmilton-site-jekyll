---
layout: post
title: Inject Javascript Into Android WebView
date: 2014-06-07 17:13:20.000000000 +10:00
---
You want to run some javascript inside a web page but don't have access to the source.

### Solution

Just use the following code to suit your needs.
```
String js = "javascript:(function () {
	// Do some JS in here
})()";
// NOTE: webView is just a reference to a some global variable in your Activity
webView.loadUrl(js);
```

It should be noted that I have had issues when not putting in the function part which wraps the comment (i.e // Do some JS in here). An example of the odd behavour is the page reloading and showing some text I was trying to inject into the currently focused element.
