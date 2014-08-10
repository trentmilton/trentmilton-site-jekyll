---
title: Sublime Text 3 Laggy
date: 2014-03-15 16:30:41.000000000 +10:00
---
I've recently upgraded Mavericks (OSX) to 10.9.2 and discovered that Sublime was performing terribly slow. I'm talking 1 second (plus) delays in keyboard stroke to render in the editor.

### Solution

My first test was simply wipe everything out from **~/Library/Application Support/Sublime Text 3**. Success, Sublime is back to its former glory. **But** I still want all my sweet settings and plugins...

Remove everything **EXCEPT Installed Packages** and **Packages**. For me that meant deleting:

- Backup
- Cache
- Index
- Local

You may have to **enter your license again** but that's nothing major.
