---
layout: post
title: Show Xcode Project Build Settings In Terminal
date: 2014-01-29 08:30:28.000000000 +10:00
tags:
  - xcode
  - build
  - xcodebuild
  - settings
  - terminal
---
[xcodebuild](https://developer.apple.com/library/mac/documentation/Darwin/Reference/ManPages/man1/xcodebuild.1.html) allows you to view all the Xcode project settings from Termina

	xcodebuild -project <project name>.xcodeproj -target <target name> -showBuildSettings

This will output all the project build settings such as:

- AD\_HOC\_CODE\_SIGNING\_ALLOWED
- FRAMEWORK\_VERSION
- GCC\_PRECOMPILE\_PREFIX\_HEADER
- VERBOSE\_PBXCP
- ...
