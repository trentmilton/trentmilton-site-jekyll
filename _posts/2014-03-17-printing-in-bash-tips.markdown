---
layout: post
title: Printing in Bash Tips
date: 2014-03-17 07:59:58.000000000 +10:00
---
Have you been stuck while trying to do some basic printing in Bash? Below are some basic problems and solutions to issue I've had with Bash printing.

### Tips

**Problem:** Tabs and new lines won't print.</br>
**Solution:** Using **echo** make sure [you put](http://stackoverflow.com/a/525873) -e which will enable interpretation of backslash escapes.


    // Without -e
	echo 'Hello\nthere'
    > hello\nthere
    // Now with -e
    echo -e 'hello\nthere'
    > hello
    > there
