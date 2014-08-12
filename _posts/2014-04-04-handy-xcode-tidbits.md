---
layout: post
title: Handy Xcode Tidbits
published: true
categories: []
tags: [xcode, ios, simulator]
---
The following are some useful bits and pieces for working with Xcode.

### General

#### iOS Simulator Laggy

With the release of Mavericks the OS had a featue called coalesing added. This is supposed to help in running iOS 6.1 and earlier. According to the Apple release note:

> Performance issues can arise when running apps within the iOS Simulator on OS X Mavericks with a simulated OS version of iOS 6.1 or earlier.
A workaround is to disable timer coalescing while using the iOS 6.1 or earlier simulator by executing the following command in a Terminal window:

	sudo sysctl -w kern.timer.coalescing_enabled=0

> (15501929)

#### Target Simulator or Device for iOS

	#if TARGET_IPHONE_SIMULATOR
	   NSString *hello = @"Hey, I'm the iOS Simulator!";
	#else
	   NSString *hello = @"Hey, I'm an iOS device!";
	#endif

#### Can't locate header files for static iOS library

You should read the response on StackOverflow [here](http://stackoverflow.com/questions/5543854/xcode-4-cant-locate-public-header-files-from-static-library-dependancy) and [here](http://stackoverflow.com/a/10855606).

The most important takeaway from it all is the following line which should go in the **User Header Search Paths** setting.

	$(PROJECT_TEMP_DIR)/../UninstalledProducts/include
