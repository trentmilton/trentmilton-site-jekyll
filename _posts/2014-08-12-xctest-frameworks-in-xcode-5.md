---
layout: post
title: XCTest Frameworks in Xcode 5
published: true
categories: []
tags: [xcode, osx, framework, xctext]
---

Have you found youself struggling to work out how to unit test with **XCTest** in **Xcode 5**? I have, and it's a pain to work out how to solve this.

You may get an error like the following in your unit test classes:

> Can't find .m file

### Solution

It's actually really simple (once someone tells you) to get this working. Just do the following:

1. Under your unit tests **Build Settings** look for the **Linker** > **Bundle Loader** setting.
2. Add the following:

	$(BUILT_PRODUCTS_DIR)/[name].framework/Versions/A/[name]

You will need to make sure you replace **[name]** with your framework name that your testing.