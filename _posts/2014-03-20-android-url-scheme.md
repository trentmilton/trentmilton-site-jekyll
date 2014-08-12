---
layout: post
title: Android URL Scheme
published: true
categories: []
tags: [android, url, scheme]
---
After working with URL schems in iOS I assumed that Android would work the same. Unfortunately this was not the case. No matter what I tried I couldn't get the Android OS to detect a custom url scheme, e.g. **shaydesdsgn://action=option**.

### Solution
The problem was that if a user enters a url scheme into a browsers address bar the browser handles the URL itself, skipping the OS's in built URL detection. In other words the browser doesn't issue a general-purpose VIEW/BROWSABLE intent when you type a URL into the location bar.

However if the URL scheme is launched via a link , everything works correctly.

The following needs to be added in order to get URL schemes working.

	<intent-filter>
		<!-- You would replace shaydesdsgn with your own URL scheme -->
		<data android:scheme="shaydesdsgn" />
		<!-- or you can use deep linking like -->
		<action android:name="android.intent.action.VIEW" />
		<category android:name="android.intent.category.DEFAULT" />
	    <category android:name="android.intent.category.BROWSABLE" />
	</intent-filter>

That's all there is to it.
