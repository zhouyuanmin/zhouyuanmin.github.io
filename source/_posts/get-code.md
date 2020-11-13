---
title: get-code
categories: Python
tags: level V
date: 2020-11-13 11:45:05
---

这个inspect库可以获取函数的源代码

```python
import inspect


def foo(arg1, arg2):
    # do something with args
    a = arg1 + arg2
    return a


lines = inspect.getsource(foo)
print(lines)
```

