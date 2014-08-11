---
layout: post
title: Install Mscgen On Mac
date: 2014-01-28 07:54:42.000000000 +10:00
tags:
  - mscgen
  - graphviz
  - doxygen
  - macports
---
[Mscgen](http://www.mcternan.me.uk/mscgen/) is used along with [Graphviz](http://www.graphviz.org/)'s dot for [Doxygen](http://www.stack.nl/~dimitri/doxygen/). If you are experiencing errors when compiling say [cocos2d](http://www.cocos2d-iphone.org/) documentation this should help. Do the following and you should be fine.

1. install [macports](http://www.macports.org/), follow [this](http://www.macports.org/install.php) guide
2. In terminal run the command: sudo port install mscgen
NOTE: make sure you have Unix tools installed from Xcode and the X11 installed or you may get the following error

	"Computing dependencies for mscgenError: Unable to execute port: can’t read "build.cmd": Failed to locate 'make' in path: '/opt/local/bin:/opt/local/sbin:/bin:/sbin:/usr/bin:/usr/sbin' or at its MacPorts configuration time location, did you move it?"

Et voilà, you should now be installing mscgen, this will take a while so sit back and relax!

You can use this same process to get many of the other ports from macports!
