---
title: Find The Process Using That Port
date: 2014-01-29 08:34:04.000000000 +10:00
---
There comes a time when you want to start up a process and find it won't work because some ninja process is already using that port.

### Solution

The following example will help find what process is using that process and terminate it (with extreme prejudice).

    // For out example find what is using port 3000
	lsof -wni tcp:3000

    // Below is the output from Terminal (bash)
    COMMAND        PID  USER   FD   TYPE ...
    NinjaProcess   816  mac    92u  IPv4 ...

	// We have found that it is PID (Process ID) 816. Let's get rid of it now
	kill -816 PID

    // Let's make sure it's gone
    lsof -wni tcp:3000
	// There is nothing displayed, this means there is nothing on port 3000 anymore.

So there you have it. A simple way to remove any process using a port. Use at your own risk though. Make sure you know you can get rid of the process or you might find your machine not running as expected.
