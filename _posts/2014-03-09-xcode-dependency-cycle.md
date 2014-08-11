---
layout: post
title: Xcode Dependency Cycle
published: true
categories: []
tags: [xcode, warning, error, build, clean, dependency, cycle]
---
Have you ever found an odd warning after a build or clean in Xcode like the following?

> Dependency cycle for target '[target]' detected: [target] -> [target]

### Solution
Under the scheme settings, in particular the **Build** phase you should see the following options:

1. Parllelize Build
2. Find Implicit Dependendencies

Turn both of these off and the warning should go away.

It is worth noting that the project in question had a UnitTest target.
