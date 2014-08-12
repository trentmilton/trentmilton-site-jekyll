---
layout: post
title: Handy Android Tidbits
published: true
categories: []
tags: [tidbits, android, activity, build, sign, apk]
---
The following are some useful bits and pieces for working with the Android SDK.

### General

#### Go back to previous Activity

	// Just call the following anywhere in the current Activity
	finish();


#### Build and sign project

	ant release -Dkey.store.password="[password]" -Dkey.alias.password="password"


#### Libraries do not get added to APK anymore after upgrade to ADT 22

To quote directly from [this](https://groups.google.com/d/msg/adt-dev/epOfZbKPFdk/RbR2VYNQ5_8J) source:

> "When upgrading, the ‘Order and Export’ of the new ‘Android Private Libraries’ is not always checked. And the android-support-v4.jar is now in this ‘Android Private Libraries’ section.

>To fix this, go to ‘Order and Export’ and check ‘Android Private Libraries’. Then refresh/clean/rebuild.

>After you done this ‘fix’ for a library project, you may need to just close and re-open any depending project, because they may not see this ‘fix’ immediately.”
