---
title: Bash Prompt Console Colours
date: 2014-04-02 08:38:25.000000000 +10:00
---
Bored of the standard colours of your output? So was I until I found a way to output colours to the terminal. I won't go into detail on how to implement the colours but I will link useful posts that go into detail about this topic below.

NOTE: You may know this under a different name: **ANSI Escape Sequences**.

### Solution

Put the following into some file loaded by bash, such as .bash_profile:

```
BLACK=$(tput setaf 0)
RED=$(tput setaf 1)
GREEN=$(tput setaf 2)
YELLOW=$(tput setaf 3)
LIME_YELLOW=$(tput setaf 190)
POWDER_BLUE=$(tput setaf 153)
BLUE=$(tput setaf 4)
MAGENTA=$(tput setaf 5)
CYAN=$(tput setaf 6)
WHITE=$(tput setaf 7)
BRIGHT=$(tput bold)
NORMAL=$(tput sgr0)
BLINK=$(tput blink)
REVERSE=$(tput smso)
UNDERLINE=$(tput smul)
ESCAPE="Esc[0m"
```

I have included a basic example [here](http://blog.shaydesdsgn.com/handy-git-tips/).

### Links

- [http://misc.flogisoft.com/bash/tip\_colors\_and\_formatting](http://misc.flogisoft.com/bash/tip_colors_and_formatting)
