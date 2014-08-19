---
layout: post
title: Verify App Store Binary Before Release
published: true
categories: []
tags: [app-store, binary, release, osx, installer, package]
---

It may be worth testing that your Mac App Store binary will actually install before submitting it for a 10+ day turnaround for review.

Apples developer [documentation](https://developer.apple.com/library/mac/documentation/IDEs/Conceptual/AppDistributionGuide/SubmittingYourApp/SubmittingYourApp.html) covers all this in great detail

I won't go into great detail except for saying that you need to **Export** as a **Mac Installer Package*** from the **Archived** section.

After which you will want to run:

	sudo installer -store -pkg path-to-package -target /

Which should give you output similar to:

	rpatel$ sudo installer -store -pkg ../Documents/TrackMix.pkg -target
	WARNING: Improper use of the sudo command could lead to data loss
	or the deletion of important system files. Please double-check your
	typing when using sudo. Type "man sudo" for more information.

	To proceed, enter your password, or type Ctrl-C to abort.

	Password:
	installer: Note: running installer as an admin user (instead of root) gives better Mac App Store fidelity
	installer: TrackMix.pkg has valid signature for submission: 3rd Party Mac Developer Installer: Ravi Patel (7U3X8B3P5Z)
	installer: Installation Check: Passed
	installer: Volume Check: Passed
	installer: Bundle com.example.rpatel.TrackMix will be installed to /Applications/TrackMix.app
	installer: Starting install
	installer: Install 0.0% complete
	installer: Install 90.8% complete
	installer: Install 100.0% complete
	installer: Finished install
	rpatel$