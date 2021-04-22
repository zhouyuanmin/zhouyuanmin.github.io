---
title: sql
categories: Messy
tags:
  - SQL
date: 2021-04-22 13:10:02
---

INSERT INTO... SELECT 与 自增id的冲突

```
1、缺少id会报错，缺少字段
2、指定id，又不确定id应该是多少
3、解决办法：设置id为null
```

```sql
-- 例子
INSERT INTO `pt_rating`.`paper_subject` SELECT
NULL AS id,  -- 这个必须有id，可以设置为null
168 AS paper_id,
subject_id,
score,
sort,
NOW() AS create_time 
FROM
	paper_subject 
WHERE
	paper_id = 167;
```

 <!-- more -->

