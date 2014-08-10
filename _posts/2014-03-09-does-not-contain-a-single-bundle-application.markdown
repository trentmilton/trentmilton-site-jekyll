---
title: Does Not Contain A Single Bundle Application
date: 2014-03-09 17:47:10.000000000 +10:00
---
You may experience a problem when trying to distribute an app to the mac app store. The following error might appear

> [target] does not contain a single bundle application.

### Solution
Go into the **Build Settings > Deployment > Skip Install** and set the **Release** to **YES**.
