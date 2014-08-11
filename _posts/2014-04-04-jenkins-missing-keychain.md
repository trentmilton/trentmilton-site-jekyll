---
layout: post
title: Jenkins Missing Keychain
published: true
categories: []
tags: [jenkins, keychain, sign]
---
If you try and use Jenkins to code sign your app you may get the following errror:

> [workspace] $ /usr/bin/security list-keychains -s ${HOME}/Library/Keychains/login.keychain
[workspace] $ /usr/bin/security default-keychain -d user -s ${HOME}/Library/Keychains/login.keychain
Will not set default: file /private/var/jenkins/Library/Keychains/login.keychain does not exist
security: SecKeychainSetDomainDefault user: Could not write to the file. It may have been opened with insufficient access privileges.
[workspace] $ /usr/bin/security unlock-keychain -p \*\*\*\*\*\*\*\* ${HOME}/Library/Keychains/login.keychain
security: SecKeychainUnlock /var/jenkins/Library/Keychains/login.keychain: The specified keychain could not be found.
FATAL: Unable to unlock the keychain.
Build step ‘XCode’ marked build as failure
Finished: FAILURE

### Solution

Go to: Keychain > Keychain First aid (from the menu)

1.	username = jenkins
2.	password = (whatever your password is)
3.	Repair

You should now be able to compile correctly.
