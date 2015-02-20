---
layout: post
title: Facebook Invalid Redirect URI
categories: []
tags: [facebook,osx,mac,desktop,app,oauth]
published: true

---

If you are having issues using Facbook authentication on a Mac app you may not have updated your configuration within the [Facebook developer console](https://developers.facebook.com).

You are most likely getting an error similar to the following:

```
{
   "error": {
      "message": "Invalid redirect_uri: Given URL is not allowed by the Application configuration.",
      "type": "OAuthException",
      "code": 191
   }
}
```

### Solution

Under [this](https://developers.facebook.com/docs/facebook-login/manually-build-a-login-flow) guide Facebook state:

> redirect_uri. The URL that you want to redirect the person logging in back to. This URL will capture the response from the Login Dialog. If you are using this in a webview within a desktop app, this must be set to https://www.facebook.com/connect/login_success.html

If you've been using [PhFacebook](https://github.com/philippec/PhFacebook) there wasn't anything you had to do until now.

However if you have been trying with a different redirect_uri, fix this up now and keep reading.

The change (it seems) is that you are now required to **explicitly set** the **redirect uri**.

1. Go to [apps](https://developers.facebook.com/apps) and select your project > Settings > Advanced > Security > Valid OAuth redirect URIs.

2. Enter the following url and wait a minute or so:

```
https://www.facebook.com/connect/login_success.html
```

That's it, test it out and hopefully it's working for you now.