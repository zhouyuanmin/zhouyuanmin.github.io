---
title: firewall
categories: Linux
tags: level V
date: 2020-11-13 10:53:33
---

# 防火墙

#### 开启端口

```
firewall-cmd --zone=public --add-port=80/tcp --permanent
```

#### 查询端口号80 是否开启

```
firewall-cmd --query-port=80/tcp
```

#### 重启防火墙

```
firewall-cmd --reload
```

#### 查询有哪些端口是开启的

```
firewall-cmd --list-port
```

#### 关闭防火墙

```
systemctl stop firewalld.service
```

#### 禁止防火墙开机自启

```
systemctl disable firewalld.service
```

#### 启动防火墙

```python
systemctl start firewalld
```

