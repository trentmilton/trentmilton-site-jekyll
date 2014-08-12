---
layout: post
title: Handy iOS UI Tidbits
published: true
categories: []
tags: [tidbits, ios, uiscrollview, uisearchbar]
---
The following are some useful bits and pieces for working with the iOS UI.

### General

#### UIScrollView content size not set correctly after autolayout update

You need to override the viewWillLayoutSubview in the appropriate view controller

	- (void) viewWillLayoutSubviews {
		[super viewWillLayoutSubview];
	    ...
	    // Here you will want to set the scroll views size correctly.
	}

The issue in question for me was the following view hierarchy:  UIViewController > UIView > UITableView > UIView (which is a header).

I found that the header resizes based on it’s content and it was larger than the scrollview initially set aside for the content on the initial render of the content size.

This will generally get called twice if you are debugging. The first before autolayout does it’s magic, then after with the value you want.

#### UISearchBar CGContext ERROR

If you get the error:

><Error>: CGContextSetBlendMode: invalid context 0x0. This is a serious error. This application, or a library it uses, is using an invalid context  and is thereby contributing to an overall degradation of system stability and reliability. This notice is a courtesy: please fix this problem. It will become a fatal error in an upcoming update.
>Terminating in response to SpringBoard’s termination.

Try deleting the following

~/Library/Preferences/com.apple.iphonesimulator.plist

#### Toggle UISearchBar for iOS 7 translucent elements

	float y = self.tableView.contentOffset.y;

	// NOTE: This topOffset only applies when the Navigation bar is translucent (iOS 7)
	float topOffset = [UIApplication sharedApplication].statusBarFrame.size.height + [[self.navigationController navigationBar] frame].size.height;
	// These offsets go down. Postive would scroll the view upwards.
	float offset = -topOffset;
	if (y < -topOffset + self.searchBar.frame.size.height) {
		offset = -topOffset + self.searchBar.frame.size.height;
	}
	[self.tableView setContentOffset:CGPointMake(0, offset) animated:YES];

#### Hide UISearchBar

	- (void) viewDidLoad {
	  [super viewDidLoad];
	  [self.tableView setContentOffset:CGPointMake(0, self.searchBar.frame.size.height)];
	}

### Links

-	[Dynamic cell height in UITableView ](http://stackoverflow.com/questions/18746929/using-auto-layout-in-uitableview-for-dynamic-cell-layouts-variable-row-heights)
