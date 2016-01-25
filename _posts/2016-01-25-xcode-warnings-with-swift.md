---
layout: post
title: Xcode Warnings With Swift
categories: []
tags: [swift,xcode,snippet]
published: True

---
With the introduction of swift goes the handy warnings that we used to love. Especially when used for TODO's, FIXME's or similar:

	#warning TODO this code is crap, make it better

There are many ways around this. I like the below for it's simplicity:

	TAGS="TODO:|FIXME:"
	echo "searching ${SRCROOT} for ${TAGS}"
	find "${SRCROOT}" \( -name "*.swift" \) -print0 | xargs -0 egrep --with-filename --line-number --only-matching "($TAGS).*\$" | perl -p -e "s/($TAGS)/ warning: \$1/"

Now when you compile you are able to see the warnings again.

If you want to take this a step further you can add some code snippets to make this process even quicker.

Just drag the following into the snipped section and put it under the relevant shortcut, I use todo.

	// TODO: <#information#>

_NOTE: You may find this doesn't work by dragging from the Xcode editor (I keep having the help show up with now info). I find it easier to just drag from Sublime or another text editor_

### Sources
- [Stack overflow](http://stackoverflow.com/a/26869489)
- [Apple developer - Creating a custom code snippet](https://developer.apple.com/library/ios/recipes/xcode_help-source_editor/chapters/CreatingaCustomCodeSnippet.html)