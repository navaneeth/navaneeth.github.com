---
layout: post
title: "nodejs0.10.2 is not backward compatible"
date: 2013-04-02 08:56
comments: true
categories: javascript, nodejs
---
I have a node module which failed to compile on node0.10.2. I have the following code.

```javascript
uv_queue_work (uv_default_loop(), &data->request, perform_learn_async, after_learn);
```

Running 

```bash
$ node-gyp build
```

will fail with error saying the 4th argument to `uv_queue_work` is incorrect. Node version 0.10.2 onwards, you have to explicitly cast the function reference to `uv_after_work_cb` to get it working. Something like,


```javascript
uv_queue_work (uv_default_loop(), &data->request, perform_learn_async, (uv_after_work_cb) after_learn);
```

I also find nodejs version numbers are not very informative. They always increase the minor and patch version and not the major version. I'd expect major version to be incremented if it has breaking changes. 
