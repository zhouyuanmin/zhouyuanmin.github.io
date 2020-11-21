---
title: create-new-branch
categories: Git
tags: 
- IV
- Git
date: 2020-11-19 15:00:08
---

#### 在一个项目中创建一个完全空白的分支

```
参数 --orphan，这个参数的主要作用有两个，一个是拷贝当前所在分支的所有文件，另一个是没有父结点，可以理解为没有历史记录，是一个完全独立背景干净的分支。
```

具体操作

```shell
# 创建一个orphan的分支，这个分支是独立的
git checkout --orphan gh-pages
# 删除原来代码树下的所有文件
git rm -rf .
# 提交初始化，才能在分支查看中出现
git commit -am "init this branch"
# 查看
git branch -a
```

 <!-- more -->

