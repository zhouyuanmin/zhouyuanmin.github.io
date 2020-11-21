---
title: django-mysql
categories: Python
tags: 
- V
- Django
date: 2020-11-20 17:36:02
---

#### Django配置mysql数据库

##### 1、安装PyMySQL

```shell
pip install PyMySQL
```

##### 2、 在Django的工程同名子目录的__init__.py文件中添加如下语句

```python
from pymysql import install_as_MySQLdb
install_as_MySQLdb()
```

<!-- more -->

##### 3、修改settings.py中DATABASES配置信息

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'HOST': '127.0.0.1',  # 数据库主机
        'PORT': 3306,  # 数据库端口
        'USER': 'root',  # 数据库用户名
        'PASSWORD': 'mysql',  # 数据库用户密码
        'NAME': 'django_demo'  # 数据库名字
    }
}
```

##### 4、在MySQL中创建数据库

```shell
create database django_demo default charset=utf8;
```

