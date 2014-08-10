---
title: Eclipse - Workbench Has Not Been Created Yet
date: 2014-03-02 14:04:06.000000000 +10:00
---
Eclipse, I could go on a rant about it but I won't (maybe another post). I booted up Eclipse today and it decided to throw me an error:

> Workbench has not been created yet

It also had some info saying that **project x** can't be built etc.

### Solution

After trying a few different [solutions](http://stackoverflow.com/questions/13773582/workbench-has-not-been-created-yet-error-in-eclipse-plugin-programming) I found the following worked for me:

1. **Project** > **Build Automatically** (turn off)
2. **Project** > **Build Working Set** > **Select Working Set...**
3. Create / Modify a working set to include the project that was missing.
4. You can turn on **Build Automatically** now. Everything should be fixed.

### Why
Honestly I didn't fully look into it but it just appears as though the default **Build Automatically** was skipping **project x**. By creating a new **Working Set** it seems to have told Eclipse everything required to stop the error from appearing.
