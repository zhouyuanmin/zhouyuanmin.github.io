---
title: pymysql
categories: Database
tags:
  - III
date: 2021-02-25 15:13:40
---

使用python操作mysql

```python
import pymysql
from pymysql import MySQLError


class MysqlDemo(object):
    def __init__(self):
        self.db = pymysql.connect(
            host="127.0.0.1",
            user="****",
            passwd="******",
            database="******",
            port=3306
        )
        self.cursor = self.db.cursor()

    def create_table(self):
        sql = ""
        self.cursor.execute(sql)  # 直接就创建了,相对"增改删",不需要数据库提交commit

    def insert_or_update_or_delete(self):  # 插入、更新、删除
        sql = ""
        self.cursor.execute(sql)
        self.db.commit()
        try:
            self.cursor.execute(sql)
            self.db.commit()
        except MySQLError as e:  # 基类
            print(e.args)
            self.db.rollback()  # db.commit失败,则需要db.rollback,记住是连接对象db的
        lines = self.cursor.rowcount  # 影响的行数 或者 返回的数据条数
        print(type(lines), lines)

    def select_data(self):
        sql = "SELECT * FROM access_log"
        self.cursor.execute(sql)
        result = self.cursor.fetchone()  # 一行数据,类似(),不可修改
        results = self.cursor.fetchall()  # 所以行的数据,类[(),()],不可修改
        lines = self.cursor.rowcount  # 影响的行数 或者 返回的数据条数
        print(type(result), result)
        print(type(results), results)
        print(type(lines), lines)

    def close(self):
        self.db.close()
```

 <!-- more -->

