---
layout: post
title: OSX FTP Server
date: 2014-03-24 08:29:47.000000000 +10:00
---
Enabling the FTP server was easy a good while ago (10.6) but times have changed. The following are some basic commands to work with the FTP server on OSX.

**Enable FTP server**

	sudo -s launchctl load -w /System/Library/LaunchDaemons/ftp.plist
