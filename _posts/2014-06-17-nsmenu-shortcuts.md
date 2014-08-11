---
layout: post
title: NSMenu Shortcuts
published: true
categories: []
tags: [osx, xcode, nsmenu, shortcut, copy, cut, paste, nstextfield]
---
Stuck trying to get **Cut, Copy & Paste** to work for an **NSTextField**? Is **Select All** letting you down? This should help you out.

### Solution
The simplest solution you can get is to first make sure you have setup the shortcuts in the **NSMenu** with a shortcut command (i.e. Command + A for Select All).

Next, Control drag from the **NSMenuItem** to the **First Responder** object in the Nib. Then scroll until to find select all. By doing this you ensure that whatever item is first responder will respond to the Command + A shortcut by doing **select all** when it can.

You would then go and link up all your other commands the same way.
