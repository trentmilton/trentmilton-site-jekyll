---
layout: post
title: 'Could not posix_spawn: error 8'
date: 2014-03-09 10:45:13.000000000 +10:00
---
Have you ever had this super secret error come up before when trying to run tests in Xcode? A quick google won't tell you too much, so what does it mean?

### Solution
Make sure you check that you have all the relevant .m files added to your **Compile Sources** tab of the test targets **Build Phases**.
