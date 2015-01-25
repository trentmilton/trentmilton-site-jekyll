---
layout: post
title: UIViewController Navigation Item
categories: []
tags: []
published: False

---

http://stackoverflow.com/questions/1449339/how-do-i-change-the-title-of-the-back-button-on-a-navigation-bar

in the parent BEFORE the push

UIBarButtonItem *newBackButton =
        [[UIBarButtonItem alloc] initWithTitle:@"NewTitle"
                                         style:UIBarButtonItemStyleBordered
                                        target:nil
                                        action:nil];
[[self navigationItem] setBackBarButtonItem:newBackButton];
[newBackButton release];
