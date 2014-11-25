---
layout: post
title: "Starting &amp; stopping redis on OS X"
date: 2014-11-25 12:32:04 +0530
comments: true
categories: [tips, osx, redis]
---

The easiest way to install `redis` on OS X is to run:

```bash
brew install redis
```

To ease starting & stopping the server, I have added the following aliases into my `.zshrc`:

```bash
alias startredis="redis-server /usr/local/etc/redis.conf"
alias stopredis="redis-cli shutdown"
```

Now I can just do *startredis* and *stopredis* to manage the redis server
