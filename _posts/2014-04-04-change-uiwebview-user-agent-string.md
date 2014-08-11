---
layout: post
title: Change UIWebView User Agent String
published: true
categories: []
tags: [user agent, uiwebview, ios]
---
Do you have a need to change the user agent string. Perhaps put in some extra information to let your server know your custom browser is calling it.

### Solution

The following will let you do just that

```
+ (void)initialize {

    // Set user agent (the only problem is that we can’t modify the User-Agent later in the program)

    NSString *userAgentString = @"Mozilla/5.0 (iPad; CPU OS 5_1 like Mac OS X) AppleWebKit/534.46 (KHTML, like Gecko) Version/5.1 Mobile/9B176 Safari/7534.48.3";
    NSDictionary *dictionnary = [[NSDictionary alloc] initWithObjectsAndKeys:userAgentString, @”UserAgent”, nil];

    [[NSUserDefaults standardUserDefaults] registerDefaults:dictionnary];

}
```

You can find a full list of user agent strings [here](http://www.webapps-online.com/online-tools/user-agent-strings/dv/operatingsystem51849/ios).
