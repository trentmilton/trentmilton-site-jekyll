---
layout: post
title: Facebook, Parse and OSX
published: false
categories: []
tags: [facebook, parse, osx, phfacebook]
---
You want to go and authenticate against Facebook for Parse on OSX. Easy you thought as they have a great little API on Parse for iOS (any everything else for that matter). But you gasp as you see the big red box proclaiming

> Facebook integration is currently only available on iOS.

### Solution

The best solution I found was to use PhFacebook. I've made a [branch](https://github.com/trentmilton/PhFacebook) of the [original](https://github.com/philippec/PhFacebook). The main reason being to make the expirey date available.

You must make sure that if you are submitting the **Mac App Store** and you have **Sandbox** enabled you add the following to you **.entitlements file** or to the **Capabilities > App Sandbox > Network** section

- com.apple.security.network.client or Incoming Connections (Server)
- com.apple.security.network.server or Outgoing Connections (Client)
