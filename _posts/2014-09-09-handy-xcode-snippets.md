---
layout: post
title: Handy Xcode Snippets
published: true
categories: []
tags: [xcode, handy, tidbit, snippet, autocomplete]
---
In Xcode you are able to create handy little code snippets and call them up via keywords. Below are ones I am using most frequently.

All you have to do is copy the code into Xcode and drag into you **Show the Code Snippet library** (it's the curly bracket {} icon) in the **Utilities** area (right side of Xcode).

**Log Object** *(log)*

	NSLog(@"%@", <#object#>);

**Shared Instance** *(singleton)*

	+ (instancetype)sharedInstance
	{
	    static dispatch_once_t once;
	    static id sharedInstance;
	    dispatch_once(&once, ^{
	        sharedInstance = [[self alloc] init];
	    });
	    return sharedInstance;
	}
