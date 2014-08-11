---
layout: post
title: Convert ERB to SLIM
date: 2014-01-25 16:33:56.000000000 +10:00
---
The following is based off the [ERB to SLIM Github project](https://github.com/slim-template/slim/wiki/Template-Converters-ERB-to-SLIM "ERB to SLIM Github project").

Run the below **command** in **Terminal** to **convert** any **.erb** files to **.slim** (skipping the regular step of converting .erb to .haml).

```language-bash
find . -name ‘*erb’ | \
xargs ruby -e ‘ARGV.each { |i| puts “html2slim -d #{i} #{i.sub(/erb$/,”slim”)}”}’ | \
bash
```
