---
title: debug-print
categories: Messy
tags: level V
date: 2020-11-12 16:48:49
---

使用print在docker中调试

```python
docker不会输出python的print(),需要这样写才会输出：加上flush=True
例子: print("debug...", flush=True)
```

<!-- more -->

