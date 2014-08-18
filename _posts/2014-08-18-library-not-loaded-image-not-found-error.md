---
layout: post
title: Library Not Loaded Image Not Found Error
published: False
categories: []
tags: []
---

Dyld Error Message:
  Library not loaded: /Library/Frameworks/EKFCommon.framework/Versions/A/EKFCommon
  Referenced from: /Users/USER/Desktop/eatkeep.app/Contents/MacOS/eatkeep
  Reason: image not found


Fix [here](http://stackoverflow.com/questions/24993752/os-x-framework-library-not-loaded-image-not-found)


**Building The Framework**

1. Add a target to create a Cocoa Framework
2. Within that targets 'Build Settings' configure the 'Installation Directory' to '@executable_path/../Frameworks'
3. Build library, and access the .framework from the archive or products directory

**Including The Framework**

1. Drag the created .framework file into the Xcode Project, be sure to tick 'Copy Files to Directory'
2. In the containing applications target, add a new 'Copy File Build Phase'
3. Set the 'Destination' to 'Frameworks'
4. Drag in the created .framework