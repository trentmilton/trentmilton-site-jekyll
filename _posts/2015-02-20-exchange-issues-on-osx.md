---
layout: post
title: Exchange Issues On OSX
categories: []
tags: [osx,exchange,microsoft]
published: true

---

Apple and Microsoft don't usually play nicely together. Especially when it comes to hooking up an Exchange account on a Mac.

### Solution

Try one or more of the following:

- Try deleting and adding your exchange account. This has fixed issues where the server rejected local changes.
- Turn off the account, close the apps and try the below, people have said this fixes a variety of issues for iCal:

```
rm ~/Library/Preferences/com.apple.iCal.*
```

- If you get the error similar to the following in iCal just try adding a new event.

> SOAPWebServicesErrorDomain Code=-997 "The operation couldn’t be completed."

-
