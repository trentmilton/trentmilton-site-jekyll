---
title: Android Cookies
---
Somewhere in your code add:

	CookieSyncManager.createInstance(context);

I will usually add this in the App.java onCreate().

Processing the cookie is done by the following


    // This is some url e.g. http://www.shaydesdsgn.com, it could actually even be "bob" if you wanted but it really doesn't make any sense to do that as it won't be automatically retrieved by the web view as it's loading URLs
    String url = ...
    // The header cookie has been extracted
    String headerCookie = ...
	for (String cookie : result.getHeaderCookies()) {
		// CookieManager doesn't add anything beyond one semi colon
		for (String part : cookie.split(";")) {
				Logger.logDebug("cookie (setting):" + part);
				CookieManager.getInstance().setCookie(url, part);
			}
        }

example

Response

	null, HTTP/1.1 200 OK
    Cache-Control, private, max-age=0
    Connection, close
    Content-Encoding, gzip
    Content-Length, 375
    Content-Type, text/xml; charset=utf-8
    Date, Sun, 02 Mar 2014 03:46:55 GMT
    Server, Microsoft-IIS/7.5
    Set-Cookie, ASP.NET_SessionId=pkydfxetk4wkjgohvbex12do; path=/; HttpOnly
    Set-Cookie, .ASPXAUTH=H298D4122669854DC85678C0F28D7FE5BE54C7DC6A7339D391937F81AAD5E3A654E94F390E6867B88AF0CE78294A1ABC14FCF7A76DED5DDD63B2476ADF47E808C0837BABC698CCA744091C38965540F0C858BD181F498AB8FB619079724852963631E0E1550DD1E2C003877382176A791427B12D1C84E2170FDA77CE2A29AEG2; expires=Tue, 04-Mar-2014 03:46:55 GMT; path=/; HttpOnly
    Vary, Accept-Encoding
    X-Android-Received-Millis, 1393732015422
    X-Android-Sent-Millis, 1393732014485
    X-AspNet-Version, 4.0.30319
    X-Powered-By, ASP.NET

Cookie

    ASP.NET_SessionId=pkydfxetk4wkjgohvbex12do; .ASPXAUTH=H298D4122669854DC85678C0F28D7FE5BE54C7DC6A7339D391937F81AAD5E3A654E94F390E6867B88AF0CE78294A1ABC14FCF7A76DED5DDD63B2476ADF47E808C0837BABC698CCA744091C38965540F0C858BD181F498AB8FB619079724852963631E0E1550DD1E2C003877382176A791427B12D1C84E2170FDA77CE2A29AEG2; expires=Tue, 04-Mar-2014 03:46:55 GMT; path=/; HttpOnly
