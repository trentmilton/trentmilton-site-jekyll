---
title: Android KitKat Permission Denial Error
date: 2014-03-20 19:27:58.000000000 +10:00
---
Testing out KitKat I found trying to send a broadcast of ACTION\_MEDIA_MOUNTED was crashing giving me an error like the following:

> Permission Denial: not allowed to send broadcast android.intent.action.MEDIA_MOUNTED kitkat

### Solution
Simply change

    sendBroadcast(new Intent(Intent.ACTION_MEDIA_MOUNTED, mediaMountUri));

to

	sendBroadcast(new Intent(Intent.ACTION_MEDIA_SCANNER_SCAN_FILE, mediaMountUri));

