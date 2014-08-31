---
layout: post
title: Push Segue Without Animation
published: true
categories: []
tags: [ios,segue,animation]
---

For a custom segue that has no push animations you can use the following:

it will appear in storyboard as 'Push No Animation'


PushNoAnimationSegue.h

	#import <UIKit/UIKit.h>

	/*
	 Move to the next screen without an animation.
	 */
	@interface PushNoAnimationSegue : UIStoryboardSegue

	@end

PushNoAnimationSegue.m

	#import "PushNoAnimationSegue.h"

	@implementation PushNoAnimationSegue

	-(void) perform{
	    UIViewController *vc = self.sourceViewController;
	    [vc.navigationController pushViewController:self.destinationViewController animated:NO];
	}

	@end

In your storyboard when you connect a view controller to another (ctrl drag, etc.) you will find a new option call 'Push No Animation'. This is based on the name you give your file above.

This was originally posted [here](http://stackoverflow.com/questions/16209113/push-segue-in-xcode-with-no-animation).