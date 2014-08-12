---
layout: post
title: Convert ERB to SLIM
published: true
categories: []
tags: [erb, slim, haml]
---
The following is based off the [ERB to SLIM Github project](https://github.com/slim-template/slim/wiki/Template-Converters-ERB-to-SLIM "ERB to SLIM Github project").

Run the below **command** in **Terminal** to **convert** any **.erb** files to **.slim** (skipping the regular step of converting .erb to .haml).

	find . -name ‘*erb’ | \
	xargs ruby -e ‘ARGV.each { |i| puts “html2slim -d #{i} #{i.sub(/erb$/,”slim”)}”}’ | \
	bash
