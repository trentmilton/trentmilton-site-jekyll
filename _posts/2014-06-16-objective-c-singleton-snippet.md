---
layout: post
title: Objective-c Singleton Snippet
published: true
categories: []
tags: [objective-c, singleton, snippet, static]
---
Sick of adding *static Class name;*, checking if it exists or running a synchronized around a sharedInstance method?

### Solution

Add the following to a snippet in xcode. This is obviously for you .m file. In case you're new you will also need to add the method name to you header.

```
+ (instancetype)sharedInstance
{
    static dispatch_once_t once;
    static id sharedInstance;
    dispatch_once(&once, ^{
        sharedInstance = [[self alloc] init];
    });
    return sharedInstance;
}
```

If you're feeling fancy you could always add a category to NSObject for this but be careful as it could easily be abused and a lot of singletons aren't a good thing.
