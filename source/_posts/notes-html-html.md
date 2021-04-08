---
title: notes-html.html
categories: Messy
tags:
  - V
date: 2021-04-08 14:38:02
---

```html
<!DOCTYPE html>
<html lang="zh-CN"> <!-- 1、记住中文 zh-CN -->
<head>
    <meta charset="UTF-8"> <!-- 2、记住编码 -->
    <title>Html Of Notes</title>
</head>
<body>
<!-- 3、记住常用标签 -->
<p>段落</p>
<br>
<h1>标题</h1>
<!-- 4、记住文本格式标签 -->
<strong>加粗</strong>
<b>加粗</b>
<em>倾斜</em>
<i>倾斜</i>
<del>删除线</del>
<s>删除线</s>
<ins>下划线</ins>
<u>下划线</u>
<!-- 5、记住div和span标签 -->
<div></div>
<span></span>
<!--6、记住图像标签-->
<img src="http://www.itcast.cn/2018czgw/images/logo.png" alt="alt图像显示不出来时显示" title="鼠标悬停的提示文本" height="100"/>
<!--7、记住超链接-->
<a href="http://www.qq.com" target="_blank">腾讯</a>
<!--8、记住表格-->
<table>
    <thead>
    <tr>
        <th>姓名</th>
        <th>性别</th>
        <th> 年龄</th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <!-- td标签 colspan="2" rowspan="2 -->
        <td>刘德华</td>
        <td>男</td>
        <td> 56</td>
    </tr>
    </tbody>
</table>
<!--9、记住列表-->
<ul>
    <li>无序列表</li>
</ul>
<ol>
    <li>有序列表</li>
</ol>
<dl>
    <dt>自定义列表</dt>
    <dd>子元素</dd>
</dl>
<!--10、记住表单-->
<form action="xxx.php" method="get">
    <!-- text 文本框 用户可以里面输入任何文字 -->
    <label>
        用户名:
        <input type="text" name="username" value="请输入用户名" maxlength="6">
    </label><br>
    <!-- password 密码框 用户看不见输入的密码 -->
    <label>
        密码:
        <input type="password" name="pwd">
    </label> <br>
    <!-- radio 单选按钮  可以实现多选一 -->
    <!-- name 是表单元素名字 这里性别单选按钮必须有相同的名字name 才可以实现多选1 -->
    <!-- 单选按钮和复选框可以设置checked 属性, 当页面打开的时候就可以默认选中这个按钮 -->
    <label>
        性别:
        男<input type="radio" name="sex" value="男">
        女<input type="radio" name="sex" value="女" checked="checked">
        人妖<input type="radio" name="sex" value="人妖">
    </label><br>
    <!-- checkbox 复选框  可以实现多选 -->
    <label>
        爱好:
        吃饭<input type="checkbox" name="hobby" value="吃饭">
        睡觉 <input type="checkbox" name="hobby">
        打豆豆 <input type="checkbox" name="hobby" checked="checked">
    </label><br>
    <!-- 点击了提交按钮,可以把 表单域 form 里面的表单元素 里面的值 提交给后台服务器 -->
    <input type="submit" value="免费注册">
    <!-- 重置按钮可以还原表单元素初始的默认状态 -->
    <input type="reset" value="重新填写">
    <!-- 普通按钮 button  后期结合js 搭配使用-->
    <input type="button" value="获取短信验证码"> <br>
    <!-- 文件域 使用场景 上传文件使用的 -->
    上传头像: <input type="file">
</form>
<!--11、记住label标签-->
<label for="text"> 用户名:</label>
<input type="text" id="text">
<!--12、记住下拉表单-->
<form>
    籍贯:
    <label>
        <select>
            <option>山东</option>
            <option>北京</option>
            <option>天津</option>
            <option selected="selected">火星</option>
        </select>
    </label>
</form>
<!--13、记住textarea标签-->
<form>
    <label>
        今日反馈:
        <textarea cols="50" rows="5">pink老师,我知道这个反馈留言是textarea来做的 </textarea>
    </label>
</form>
<!--14、记住头部标签-->
<header>头部标签</header>
<!--15、记住导航栏标签-->
<nav>导航栏标签</nav>
<!--16、记住区域标签-->
<section>
    某个区域标签
    <!--17、记住视频标签-->
    <video src="https://www.baidu.com/mi.mp4" autoplay="autoplay" muted="muted" loop="loop"
           poster="https://www.baidu.com//mi.png">视频标签
    </video>
    <!--18、记住音频标签-->
    <audio src="https://www.baidu.com//music.mp3" autoplay="autoplay" controls="controls">音频标签</audio>
    <!--19、记住新增的input表单类型-->
    <!-- 我们验证的时候必须添加form表单域 -->
    <form action="">
        <ul>
            <li><label>邮箱:<input type="email"/></label></li>
            <li><label>网址: <input type="url"/></label></li>
            <li><label>日期: <input type="date"/></label></li>
            <li><label>时间: <input type="time"/></label></li>
            <li><label>数量: <input type="number"/></label></li>
            <li><label>手机号码: <input type="tel"/></label></li>
            <li><label>搜索: <input type="search"/></label></li>
            <li><label>颜色: <input type="color"/></label></li>
            <!-- 当我们点击提交按钮就可以验证表单了 -->
            <li><input type="submit" value="提交"></li>
        </ul>
    </form>
</section>
</body>
</html>
```

