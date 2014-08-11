---
layout: post
title: iCloud Ubiquity Container Error
published: true
categories: []
tags: [icloud, ubiquity, error, container, sandbox]
---
### Problem

You are receiving an error like:

	The requested container identifier is not permitted by the client's com.apple.developer.ubiquity-container-identifiers entitlement


### Solution

Most likely if you check the .entitlements file you will find an entitlement like **com.apple.developer.icloud-container-identifiers**. If this is the case then change them to **com.apple.developer.ubiquity-container-identifiers**.

or;

You have enabled iCloud's **CloudKit** which is still in pre-release. Basically you just have to go the the app id in the developer portal and delete any associated iCloud containers attached to it. The original answer can be found [here](https://devforums.apple.com/message/992625#992625).