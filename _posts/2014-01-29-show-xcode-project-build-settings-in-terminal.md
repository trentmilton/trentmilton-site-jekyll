---
layout: post
title: Show Xcode Project Build Settings In Terminal
published: true
categories: []
tags: [xcode, build, xcodebuild, settings, terminal]
---
[xcodebuild](https://developer.apple.com/library/mac/documentation/Darwin/Reference/ManPages/man1/xcodebuild.1.html) allows you to view all the Xcode project settings from Termina

	xcodebuild -project <project name>.xcodeproj -target <target name> -showBuildSettings

This will output all the project build settings such as:

- AD\_HOC\_CODE\_SIGNING\_ALLOWED
- FRAMEWORK\_VERSION
- GCC\_PRECOMPILE\_PREFIX\_HEADER
- VERBOSE\_PBXCP
- ...
