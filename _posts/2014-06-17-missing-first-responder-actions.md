---
layout: post
title: Missing First Responder Actions
published: true
categories: []
tags: [xcode, osx, objective-c, nsresponder]
---
You've implemented the **Undo** action, go to add the redo and... there is nothing there.

### Solution
Add the following to any files .h, connect it up in the Nib / Storyboard and then you can delete it.

```
@interface NSResponder (Redo)
- (IBAction)redo:(id)sender;
@end
```

This should work for any action you want. For some reason it's a bug in Xcode with no fix at the time of writing.
