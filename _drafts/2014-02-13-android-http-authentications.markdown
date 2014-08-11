---
layout: post
title: Android HTTP Authentications
---
App.java

	@Override
	public void onCreate() {
		super.onCreate();

		CookieSyncManager.createInstance(this);
	}


After login

	CookieSyncManager.getInstance().sync();


HTTP Post

	String url = ... //
    String server = ... // Would generally be the main part of the url, wherever the cookie would have been
	HttpPost post = new HttpPost(url);
    String cookie = CookieManager.getInstance().getCookie(server);
    post.addHeader("Cookie", cookie);


TODO mention the orig server output from the cookiestore, print an example header cookie


new BasicHeader(SM.SET_COOKIE,
"__RequestVerificationToken=Ti3OsH2Ha_ilNk5Tzw6tBHxcKN-kpMGw_5h6HYYWrVjLhezhrFqo9VglDduS89HzZBnNppMvfcMi0QIKfQBgJjNsvksu8hWvoYFPGoAHGO41;
ASP.NET_SessionId=gf0lfbmvypskmia14wplamqh;
path=/;
HttpOnly;
.ASPXAUTH=60806F1196E796757FB2CB0E9561D15FCCAAF5C6BFD7D1AACBEDA0063C3D0E2074EBBA3A89E74D55FD05FE0C6D1EE058849B8E4BB62F96E4F300729A16760268557F7FE9DE5C4D00E2D2549E376887A7EC3D7E744ACC6F72222AF1F696A00CC7AF94856B5C705CF2E40D49BC91D39BB6");



{
    Cookie = "
    .ASPXAUTH=0FA093D3F22B3B97063D6D99419474F51353C379332C63389E3BB290550AC190304359EDEA582F1950BDDB37EBF64181C3131AC532D80DDCBD58EE6A66F9A7FD5DB562B871A8FBAA07C297C1FE8C440F92F864FC0B7CF7842D1531D54A6A5AD156F847E3928C2C24DA7FD9AB90A9C03A;
    __RequestVerificationToken=jlW33Xc_Eipg69YS9qZjJXxMSZFm7-nO3y4oP0ez_i0PGMWHiId1_hl7RspYaw-r9xwlm2cZSRvoZHoLFu0zuNvC9wIseJCMy1k4YxI-BX41;
    ASP.NET_SessionId=fmehz0f5wt2xex0jrzfrm4fh";

    accept = "text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8";
    "accept-encoding" = gzip;
    "content-type" = "multipart/form-data; boundary=---------------------------17237809831461299884346131229";
    "user-agent" = "unirest-objc/1.1";
}
