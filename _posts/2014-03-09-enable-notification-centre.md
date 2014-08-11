---
layout: post
title: Enable Notification Centre
published: true
categories: []
tags: [notification, centre, osx]
---
If you have disabled notification centre you may be having a hard time turning it back on.

### Solution
Run the following in **Terminal**.

	sudo defaults write /System/Library/LaunchAgents/com.apple.notificationcenterui KeepAlive -bool true

    launchctl load -w /System/Library/LaunchAgents/com.apple.notificationcenterui.plist
