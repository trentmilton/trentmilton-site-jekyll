---
layout: post
title: Handy OSX UI Tidbits
published: true
categories: []
tags: [tidbits, osx, ui, nsbutton, modal, window]
---
The following are some useful bits and pieces for working with the OSX UI.

### General

#### NSButton Content Alignment

	// The space between the image and text
	CGFloat spacing = 6.0;

	// Lower the text and push it left so it appears centered below the image
	CGSize imageSize = button.imageView.frame.size;
	button.titleEdgeInsets = UIEdgeInsetsMake(0.0, -imageSize.width, -(imageSize.height + spacing), 0.0);

	// Raise the image and push it right so it appears centered above the text
	CGSize titleSize = button.titleLabel.frame.size;
	button.imageEdgeInsets = UIEdgeInsetsMake(-(titleSize.height + spacing), 0.0, 0.0, -titleSize.width);

### Errors

#### Modal session requires modal window

	@implementation MainWindowController {
	    PreferencesWindowController *_preferencesWC; // This is simply a NSWindowController
	}

	- (void) awakeFromNib {
	    [super awakeFromNib];

	    _preferencesWC = [[PreferencesWindowController alloc] initWithWindowNibName:@"PreferencesWindow"];
	}

	- (IBAction) menuShowPreferences:(id)sender {
	    if ([self.window attachedSheet] == nil) {
	        [NSApp beginSheet:_preferencesWC.window
	           modalForWindow:self.window
	            modalDelegate:self
	           didEndSelector:@selector(didEndSheet:returnCode:contextInfo:)
	              contextInfo:nil];
	    }
	    else {
	        [NSApp endSheet:_preferencesWC.window];
	    }
	}

	- (void) didEndSheet:(NSWindow *)sheet returnCode:(NSInteger)returnCode contextInfo:(void *)contextInfo {
	    [sheet orderOut:self];
	}
