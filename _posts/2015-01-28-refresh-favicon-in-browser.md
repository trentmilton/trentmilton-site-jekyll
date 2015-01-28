---
layout: post
title: Refresh favicon in browser
categories: []
tags: [favicon, web, browser]
published: true

---
If you've ever had an issue with a favicon being cached you can do the following to refresh the favicon for a specific site.

### Solution

1. Navigate to the location of the favicon e.g. yourdomain.com/favicon.ico
2. Refresh you the a page on your domain
3. The favicon is now updated

NOTE: If the favicon is somewhere else you'll have to navigate to there. Look for the following (or something similar) in the markup:

	<link rel="icon"
		type="image/png"
		href="/somewhere/favicon.ico" />

If you still can't find it read over [this](https://en.wikipedia.org/wiki/Favicon) Wiki entry for possible ways the favicon is setup.
