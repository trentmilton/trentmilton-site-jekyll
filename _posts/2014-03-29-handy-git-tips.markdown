---
title: Handy Git Tidbits
date: 2014-03-29 21:33:48.000000000 +10:00
---
The following are some useful bits and pieces for working with git.

### Commands

-	**Push all remotes at once**: git remote | xargs -L 1 git push
-	**Disconnect from repository**: rm -rf .git

### Bash Alias's

You can add the following to your .bash_profile which help speed up your git'n:

```
alias gita="git add -A"
alias gitc="git commit -m $1"
alias gitl="git log"
alias gitp="git push"
alias gits="git status"
alias gitu="git ls-files . --exclude-standard --others"
```

If you want a way to print out the alias's (as the list could grow really large) add the following:

```
// There are plenty more colours you can use, see below.
BLUE=$(tput setaf 4)
NORMAL=$(tput sgr0)

// This function will get the alias text and output it to the console for you.
function formataliashelp() {
	local item
	while [ ${#} -gt 0 ]; do
		item=${1}
		alias $item | sed "s/alias $item=//" | { read LINE; echo -e ${BLUE}$1${NORMAL}'\t'"$LINE"; }
		shift
	done
}

// This is what you call
alias gith="formataliashelp gita gitc gitl gitp gits gitu"
```

- If you want a full list of colours refer to this [post](http://blog.shaydesdsgn.com/bash-prompt-console-colours/).

### Links
- [Official git documentation ](http://git-scm.com/documentation)
- [Git cheatsheet](http://ndpsoftware.com/git-cheatsheet.html)

Have any suggestions for more content? Comment below...
