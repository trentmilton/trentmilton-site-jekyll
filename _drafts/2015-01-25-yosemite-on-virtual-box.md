---
layout: post
title: Yosemite on Virtual Box
categories: []
tags: []
published: False

---
1. http://www.jacobtomlinson.co.uk/2014/06/07/how-to-install-os-x-yosemite-developer-preview-in-virtualbox/

2. fix resolution
"3.12.1. Video modes in EFI

EFI provides two distinct video interfaces: GOP (Graphics Output Protocol) and UGA (Universal Graphics Adapter). Mac OS X uses GOP, while Linux tends to use UGA. VirtualBox provides a configuration option to control the framebuffer size for both interfaces.

To control GOP, use the following VBoxManage command:

VBoxManage setextradata "VM name" VBoxInternal2/EfiGopMode N

Where N can be one of 0,1,2,3,4,5 referring to the 640x480, 800x600, 1024x768, 1280x1024, 1440x900, 1920x1200 screen resolution respectively."

For example, to set my OS X guest's resolution to 1440x900 I ran

$ VBoxManage list vms
"OS X 10.10 - Yosemite" {d1e8cd08-babb-4822-bf60-ece94491daa8}

$ VBoxManage setextradata "OS X 10.10 - Yosemite" VBoxInternal2/EfiGopMode 4

3.
Guest additions
