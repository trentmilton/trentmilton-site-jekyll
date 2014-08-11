---
layout: post
title: Testing Cocoa Frameworks
published: true
categories: []
tags: [test, cocoa, osx, framework]
---

You are trying to run unit tests (XCTest) against a Cocoa Framework you are writing and it's throwing errors. Such as:

1. Resource not found...
2. Can't find dependant framework (e.g. Parse)

### Solution
1. Link Binary With Libraries (Add the framework that's erroring).
2. Copy Files: Set the Destination to **Products Directory** and add the framework.