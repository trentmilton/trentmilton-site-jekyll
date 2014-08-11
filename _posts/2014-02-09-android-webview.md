---
layout: post
title: Android WebView Uncaught TypeError
published: true
categories: []
tags: [android, webview, error]
---
Do you have a WebView that is failing to render a page correctly? Perhaps you've looked at logcat (or whatever you are logging with) and seen an error similar to
Error

	02-11 11:18:41.164: E/Web Console(1024): Uncaught TypeError: Cannot read property 'some-property' of null at https://example-site.com/example.js:609

### Solution

The simple solution is to ensure the WebView has the following setting enabled:

	WebView webView = new WebView(this); // this is the context
	webView.getSettings().setDomStorageEnabled(true);


The documentation [states](http://developer.android.com/reference/android/webkit/WebSettings.html#setDomStorageEnabled(boolean))
> public synchronized void **setDomStorageEnabled** (boolean flag)

> Sets whether the DOM storage API is enabled. The default value is false.

>Parameters
flag	true if the WebView should use the DOM storage API

### Why

This allows the browser to store a DOM model of the page elements, so that Javascript can perform operations on it.

### Notes
- This works only from api 7.
