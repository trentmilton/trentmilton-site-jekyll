---
layout: post
title: Using Gmail With a Custom Domain
published: true
categories: []
tags: [gmail,mailgun,domain,alias]
---
Instead of paying for a [Google apps](https://www.google.com/work/apps/business/) account or similar to host your email there is a free alternative.

By using [Mailgun](http://www.mailgun.com/) you can point any email address for domains you own to a gmail address.

For the example you have a gmail address of **franklin@gmail.com** and a domain of **fans.com** for which you want an email of **contact@fans.com**.

This guide is not robust and assumes you are familiar with mucking around in your domain registrar and can find your way around techy sites.

### 1. Mailgun

- Create a [Mailgun](http://www.mailgun.com/) account. **Make sure you setup the MX records under your domain registrar**.
- Add a domain, click it and verify all the settings. In this case the domain is fans.com.
- Create a route for each custom email for your domain you want. The following is an example for forwarding from your custom domain to your gmail account:
	- **Priority**: 0
	- **Filter expression**: match_recipient("contact@fans.com")
	- **Action**: forward("franklin@gmail.com")
	- **Description**: Forward contact@fans.com to franklin@gmail.com

That's it for this part, now off to Gmail.

### 2. Gmail alias

This is an optional step which allows you to send from your gmail address under an alias of your custom domain email. That is, from franklin@gmail.com it will appear to others as if your email is contact@fans.com.

- In mailgun select your **domain** and go to **Manage SMTP credential**. Create a SMTP credential for the alias you want. In this case it's contact@fans.com. Take note of the password as you'll need it later.
- In Gmail go **Settings** > **Accounts and Import** > **Send mail as**. Fill in all the details which are a combination of the SMTP user you just created and the Domain information from mailgun.

That's it! You can now use this alias to send your emails. Some Apps also allow you to use this alias to send.