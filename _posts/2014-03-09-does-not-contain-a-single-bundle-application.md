---
layout: post
title: Does Not Contain A Single Bundle Application
published: true
categories: []
tags: [app-store, mac, osx, bundle, application, deploy, release]
---
You may experience a problem when trying to distribute an app to the mac app store. The following error might appear

> [target] does not contain a single bundle application.

### Solution
Go into the **Build Settings > Deployment > Skip Install** and set the **Release** to **YES**.
