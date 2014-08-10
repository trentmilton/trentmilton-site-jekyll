---
title: Automate Build Number In Xcode
date: 2014-03-13 17:36:08.000000000 +10:00
---
Have you ever wanted a really big number to go against your projects in Xcode. Want no more. There is a way to have the build number increment everytime you compile (COMMAND+B).

### Solution
1. In the **Targets** **Build Phases** add a **Run Script** Phase, Editor > Add Build Phase > Add Run Script Build Phase
2. Add the following snippet of code

	buildPlist=$PRODUCT_NAME"/"$PRODUCT_NAME"-Info.plist"
	CFBundleVersion=$(/usr/libexec/PlistBuddy -c "Print CFBundleVersion" $buildPlist)
	CFBundleVersion=$(($CFBundleVersion + 1))
	/usr/libexec/PlistBuddy -c "Set :CFBundleVersion $CFBundleVersion" $buildPlist

You just have to make sure that you set the **Build** to an integer and **NOT** leave it as the **1.0** which it is set to by default.
