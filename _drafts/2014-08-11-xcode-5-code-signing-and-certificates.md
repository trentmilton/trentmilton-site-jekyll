---
layout: post
title: Xcode 5 Code Signing and Certificates
published: true
categories: []
tags: [xcode, signing, cerfificate, ios, osx]
---
Are you trying to work out wtf is going on with code signing, certificates etc. It probably doesn't make any sense to you right?

Luckily Xcode 5 has simplified (perhaps too much) the whole process so there usually isn't anything you have to worry about.

The main pieces involved are:

- **Certificates** These are used to do signing. Xcode can automatically sort these out for you when needed.
- **App IDs** This is what makes your app unique. You will need to pop on over [here](http://developer.apple.com) and make one for production.
- **Provisioning profiles** This is used to validate against the app store (Basically to let you on it).






