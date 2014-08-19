---
layout: post
title: Library Not Loaded Image Not Found Error
published: true
categories: []
tags: [osx, framework, app store, error]
---
Recently I ran into an error submitting [eatkeep](http://www.eatkeep.io) to the Mac App Store. As it will eventually be a universal app (ios, mac) I created a project that generates a framework (mac) and a static library (ios).

The problem came upon review and receiving the following error from a stacktrace from the reviewer:

> Dyld Error Message:
		Library not loaded: /Library/Frameworks/[framework-name].framework/Versions/A/[framework-name]
		Referenced from: /[path]/[app-name].app/Contents/MacOS/[app-name]
		Reason: image not found

### Solution

The problem was due to the **Installation Directory** not being set correctly. You can find this setting under the **Frameworks Build Settings.**

What I had was:

> $(LOCAL_LIBRARY_DIR)/Frameworks

and what I needed was:

> @executable_path/../Frameworks

I found the solution on [Stack Overflow](http://stackoverflow.com/questions/24993752/os-x-framework-library-not-loaded-image-not-found) and further information from [Apple](https://developer.apple.com/library/mac/documentation/MacOSX/Conceptual/BPFrameworks/Tasks/CreatingFrameworks.html#/apple_ref/doc/uid/20002258-BAJDHDAF). The Apple documentation is useful so it's worth a read over

The following has been extracted from the links mentioned above and should be enough to help fix this issue.

**Building The Framework**

1. Add a target to create a Cocoa Framework
2. Within that targets 'Build Settings' configure the 'Installation Directory' to '@executable_path/../Frameworks'
3. Build library, and access the .framework from the archive or products directory

**Including The Framework**

1. Drag the created .framework file into the Xcode Project, be sure to tick 'Copy Files to Directory'
2. In the containing applications target, add a new 'Copy File Build Phase'
3. Set the 'Destination' to 'Frameworks'
4. Drag in the created .framework