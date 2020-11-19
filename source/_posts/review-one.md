---
title: review-one
categories: Review
tags: level V
date: 2020-11-12 16:40:18
---

**复习-one**

1.创建项目

```
django-admin startproject meiduo_mall
```

2.创建数据库

```
create database meiduo_mall charset=utf8;
```

3.创建用户

```
create user itcast identified by '123456';
```

4.授权

```
grant all on meiduo_mall.* to 'itcast'@'%';
```

5.刷新

```
flush privileges;
```

<!-- more -->

6.日志

```
logger = logging.getLogger('django')
logger.debug('测试logging模块debug')
```

7.创建app

```
python ../../manage.py startapp users
```

8.HTTP动词

```
GET（SELECT）：从服务器取出资源（一项或多项）。
POST（CREATE）：在服务器新建一个资源。
PUT（UPDATE）：在服务器更新资源（客户端提供改变后的完整资源）。
DELETE（DELETE）：从服务器删除资源。
# 不常用如下：
PATCH（UPDATE）：在服务器更新(更新)资源（客户端提供改变的属性）。
HEAD：获取资源的元数据。
OPTIONS：获取信息，关于资源的哪些属性是客户端可以改变的。
```

9.过滤信息

```
?limit=10：指定返回记录的数量
?offset=10：指定返回记录的开始位置。
?page=2&per_page=100：指定第几页，以及每页的记录数。
?sortby=name&order=asc：指定返回结果按照哪个属性排序，以及排序顺序。
?animal_type_id=1：指定筛选条件
```

10.状态码

```
200 OK - [GET/PUT/PATCH]：服务器成功返回用户请求的数据
201 CREATED - [POST]：用户新建或修改数据成功。
202 Accepted - [*]：表示一个请求已经进入后台排队（异步任务）
204 NO CONTENT - [DELETE]：用户删除数据成功。
400 INVALID REQUEST - [POST/PUT/PATCH]：用户发出的请求有错误，服务器没有进行新建或修改数据的操作
401 Unauthorized - [*]：表示用户没有权限（令牌、用户名、密码错误）。
403 Forbidden - [*] 表示用户得到授权（与401错误相对），但是访问是被禁止的。
404 NOT FOUND - [*]：用户发出的请求针对的是不存在的记录，服务器没有进行操作，该操作是幂等的。
406 Not Acceptable - [GET]：用户请求的格式不可得（比如用户请求JSON格式，但是只有XML格式）。
410 Gone -[GET]：用户请求的资源被永久删除，且不会再得到的。
422 Unprocesable entity - [POST/PUT/PATCH] 当创建一个对象时，发生一个验证错误。
500 INTERNAL SERVER ERROR - [*]：服务器发生错误，用户将无法判断发出的请求是否成功。
```

11.前端

```
 v-cloak 使变量在渲染出来前隐藏. 渲染出来后, 显示.
 @blur="check_username"
 v-show="error_name"
 v-model="password"
 @submit="on_submit"
 window.event.returnValue = false
 <img :src="image_code_url"> 
 @click="send_sms_code"
 [[ error_sms_code_message ]]
 <a href="{{ url('goods:detail', args=(sku.id,)) }}">{{ sku.name }}</a>
```

12.后端方法

```python
return http.HttpResponseForbidden('请勾选用户协议')
```

```python
try:
    User.objects.create_user(username=username, password=password, mobile=mobile)
except DatabaseError:
    return render(request, 'register.html', {'register_errmsg': '注册失败'})
```

```python
return http.HttpResponse('注册成功，重定向到首页')
```

```python
return redirect(reverse('contents:index'))
```

```python
login(request, user)
logout(request)
# 进行判断: 是否登录验证
if request.user.is_authenticated():
```

```
请求地址 /usernames/(?P<username>[a-zA-Z0-9_-]{5,20})/count/
```

```
count = User.objects.filter(username=username).count()
```

```
redis_conn = get_redis_connection('verify_code')
redis_conn.setex('img_%s' % uuid, 300, text)
redis_conn.get('img_%s' % uuid)
redis_conn.delete('img_%s' % uuid)
```

```
return http.HttpResponse(image, content_type='imgae/jpg')
```

```
http.JsonResponse({'code': RETCODE.OK, 'errmsg': '发送短信成功'})
```

```
pl = redis_conn.pipeline()
pl.setex('sms_%s' % mobile, 300, sms_code)
pl.setex('send_flag_%s' % mobile, 60, 1)
pl.execute()
```

```python
# 设置状态保持的周期
if remembered != 'on':
    # 不记住用户：浏览器会话结束就过期
    request.session.set_expiry(0)
else:
    # 记住用户：None 表示两周后过期
    request.session.set_expiry(None)
```

```
http.HttpResponseNotFound('GoodsCategory 不存在')
```

13.cookie

```
response = redirect(reverse('contents:index'))
response.set_cookie('username', user.username, max_age = 3600 * 24 * 15)
response.delete_cookie('username')
```

14.异常

```
except GoodsCategory.DoesNotExist:
```

