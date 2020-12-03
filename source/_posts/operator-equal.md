---
title: operator-equal
categories: Python
tags:
  - V
  - Python
date: 2020-12-03 16:16:32
---

### 比较两个对象是否完全相等

方法1，使用==

```
a = {'a': 1, 'b': 2}
b = {'a': 1, 'b': 2}
c = {'a': 1, 'b': 3}

print(a == b)  # True
print(a == c)  # False
```

方法2，使用operator

```
import operator

a = {'a': 1, 'b': 2}
b = {'a': 1, 'b': 2}
c = {'a': 2, 'b': 2}
print(operator.eq(a, b))  # True
print(operator.eq(a, c))  # False
```

 <!-- more -->