---
layout: post
title: Install PostGres Gem For Mac
date: 2014-01-25 16:34:43.000000000 +10:00
---
1. **Download** the [PostGres app](http://postgresapp.com/ "Postgres app download") and drop it into your **Applications** folder.
2. **Run** the following command in **Terminal** (or whatever you use). Just make sure you pay attention the the **location** of the .app file.

```language-bash
gem install pg — —with-pg-config=/Applications/Postgres93.app/Contents/MacOS/bin/pg_config
```

That's all there is to it.
