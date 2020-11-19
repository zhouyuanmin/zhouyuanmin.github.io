---
title: review-four
categories: Review
tags: level V
date: 2020-11-13 01:01:42
---

一、linux环境

```
执行命令，如何在任何目录下都可以执行这个命令
# 查找“指定命令”的完整路径，格式：find / -name 命令名
find / -name mysqladmin
# 把路径直接链接到/usr/bin下，格式：ln -s 指定命令的路径 /usr/bin
ln -s /usr/local/mysql/bin/mysqladmin /usr/bin
```

<!-- more -->

二、python虚拟环境

```
创建空的虚拟环境，pip指定位pip3，python指定位python3
# 安装python3的虚拟环境包，格式：pip3 install virtualenv
例子：pip3 install virtualenv
# 执行命令，加上--no-site-packages，格式：virtualenv --no-site-packages 虚拟环境名
例子：virtualenv --no-site-packages test
# 进入命令，格式：source 虚拟环境名/bin/activate
例子：source test/bin/activate
# 退出命令，格式：deactivate
例子：deactivate
```

```python
# 1.安装python3
yum install python36
# 2.安装virtualenv和virtualenvwrapper
pip3 install virtualenv
pip3 install virtualenvwrapper
# 3.配置信息
vim ~/.bashrc
# 在末尾加上如下信息：
---------------------------
# virtualenvwrapper配置
export WORKON_HOME=/home/dev/virtualenv   # 指定虚拟环境存放的目录 
export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3     #指定python解释器
source /usr/local/bin/virtualenvwrapper.sh  # 执行脚本
---------------------------
source ~/.bashrc
# 4.常见命令
mkvirtualenv -p python3 虚拟环境名称  # 创建一个python3的虚拟环境
deactivate                # 退出当前虚拟环境
workon [虚拟环境名称]       # 使用某个虚拟环境
rmvirtualenv [虚拟环境名称] # 删除某个虚拟环境
lsvirtualenv              # 列出所有虚拟环境
# 5.包管理
# 导出
pip freeze -l > packages.txt  # 其中-l参数是只列出当前虚拟环境的包（字母l）
# 导入
pip install -r packages.txt
```

```
# window环境
# 1.安装virtualenv和virtualenvwrapper
pip install virtualenv
pip install virtualenvwrapper-win
# 2.指定虚拟环境存放的目录（配置系统环境变量）
变量名：WORKON_HOME
变量值：指定路径即可，eg：D:\virtualenv
# 3.其他等同于linux环境
```

