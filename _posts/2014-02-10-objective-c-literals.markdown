---
layout: post
title: Objective-C Literals
date: 2014-02-10 07:35:33.000000000 +10:00
---
Have you ever wanted to quickly write an NSNumber without having to do the following:

	NSNumber *pi = [NSNumber numberWithFloat:3.14f]; // Could be numberWithInt, numberWithBool etc.

### Solution

Well the wait is over. Actually it has been for quite a while. You can use Objective-c literals to get the job done. The aforementioned code can be written as:

	NSNumber *pi = @3.14;

This is available when using the Apple LLVM Compiler 4.0 and above. I won't go into great detail about other uses for it but further details can be found in the references below.

### References

- Clang 3.5 documentation (Objective-c Literals): http://clang.llvm.org/docs/ObjectiveCLiterals.html
- Detailed examples of both Objective-c literals and boxed expressions: http://code.tutsplus.com/tutorials/objective-c-literals--mobile-12882
