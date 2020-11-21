---
title: match-zh
categories: Develop
tags: 
- V
- Re
date: 2020-11-13 11:48:11
---

### 正则匹配中文

```
import re
title = '你好，hello，世界'
pattern = re.compile(r'[\u4e00-\u9fa5]+')
result = pattern.findall(title)
print(result)
```

