---
layout: post
title: Printing in Bash Tidbits
published: true
categories: []
tags: [bash, printing, log, tidbits]
---
Have you been stuck while trying to do some basic printing in Bash? Below are some basic problems and solutions to issue I've had with Bash printing.

### Printing new lines

Using **echo** make sure [you put](http://stackoverflow.com/a/525873) -e which will enable interpretation of backslash escapes.


    // Without -e
	echo 'Hello\nthere'
    > hello\nthere
    // Now with -e
    echo -e 'hello\nthere'
    > hello
    > there
