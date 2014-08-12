---
layout: post
title: Testing Cocoa Frameworks
published: true
categories: []
tags: [test, cocoa, osx, framework]
---

You are trying to run unit tests (XCTest) against and it's complaining it can't find a framework that's a dependency e.g. Parse.

### Solution

Under your unit test's **Build Phases**:

1. **Link Binary With Libraries**: add the framework that's erroring.
2. **Copy Files**: set the Destination to **Products Directory** and add the framework.