---
title: scrapy-shell
categories: Python
tags: 
- V
- Scrapy
date: 2020-11-13 11:29:45
---

#### 使用scrapy的shell测试网站

```python
# 给scrapy shell 调试加上headers
scrapy shell # 进入shell,但没有url
headers = {'User-Agent': 'User-Agent:Mozilla/5.0 (Windows NT 6.1; rv:2.0.1) Gecko/20100101 Firefox/4.0.1'}
req = scrapy.Request(url='url',headers=headers)
fetch(req) # 如此就等价于scrapy shell url # 添加了headers
```

<!--more-->