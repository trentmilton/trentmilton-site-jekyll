---
layout: post
title: App Sandbox Not Enabled
date: 2014-03-10 19:34:46.000000000 +10:00
---
If you have had to spend a few days (or still are if you're desparate enought to be here) trying to get your app working with sandbox I might be able to help.

I'm assuming you have alredy tried the following under the project properties:

1. Targets > Capabilities > App Sandbox > Turn **ON**
2. General > Signing > Mac App Store
3. Build Setting > Code Signing > Provisioning Profile > [Some rovisioning profile you have already set up]

If this solves your problem awesome, then I'm no further use to you. Otherwise read on my friend.

### Solution

For me I thought I was really clever by putting a **Copy Files** build phase which would copy the compiled binary over to a Dropbox folder for use later on.

I then thought I was clever by fixing a warning (honestly can't remember what it was now) by going under the **Build Settings** and setting **Skip Install** for **Release** to **YES**.

What did this do I hear you think. It produced a folder structure like the following:

	[target datestamp].xcarchive/Products/Users/[me]/Dropbox/Applications/[target].app

When I peaked inside the .app I didn't find the following important files & folders:

- _CodeSignature [folder]
- embedded.provisionprofile [file]
- **Resources/archived-expanded-entitlements.xcent** [file]

The most important one is is the **entitlements** file, as I had skipped the install the archive was simply archiving the copied target that was going to dropbox

---

Up until now I've told you what I did wrong. What I did to fix this was as follows.

1. Delete the **Copy Files** build phase.
2. Set the **Skip Install** to **NO** for **ALL Configurations** i.e. Debug & Release in my case.

Once I ran **Archive** my folder structure was correct and my app was on the following path:

	[target datestamp].xcarchive/Products/Applications/[target].app

---

On a side note, you'll find that if you leave in the **Copy Files** you will have both build paths within your .xarchive folder. Which means you get a funky icon instead of your app icon. This happens because there are **two** targets in the archive instead of the expected **one**.
