---
layout: post
title: 'Could not posix_spawn: error 8'
published: true
categories: []
tags: [error, posix_spawn, xcode, test]
---
Have you ever had this super secret error come up before when trying to run tests in Xcode? A quick google won't tell you too much, so what does it mean?

### Solution
Make sure you check that you have all the relevant .m files added to your **Compile Sources** tab of the test targets **Build Phases**.
