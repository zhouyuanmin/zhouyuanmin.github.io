---
title: linux-test
categories: Linux
tags:
  - Linux
date: 2020-12-23 11:48:23
---

Linux试题笔记

------

![image-20201223114914637](https://gitee.com/zhouyuanmin/images/raw/master/imgs/20201223114914.png)

----

![image-20201228163615713](https://gitee.com/zhouyuanmin/images/raw/master/imgs/20201228163615.png)

-----

 <!-- more -->

![image-20201228164022467](https://gitee.com/zhouyuanmin/images/raw/master/imgs/20201228164022.png)

-----

![image-20201228164329162](https://gitee.com/zhouyuanmin/images/raw/master/imgs/20201228164329.png)

----

1、Linux文件权限一共10位长度，分成四段,每段的含义

```
Linux用户分为：拥有者、组群(Group)、其他（other）
linux中的文件属性过分四段，如  -rwzrwz---
第一段  -  是指文件类型 表示这是个普通文件
文件类型部分
-：文件
d：文件夹
l：链接文件，可以理解为 windows中的快捷方式（link file）
b：供存储周边设备
c：一次性读取装置
 
第二段  rwz  是指拥有者具有可读可写可执行的权限  
类似于windows中的所有者权限比如 administrator 对文件具有 修改、读取和执行权限
 
第三段  rwz 是指所属于这个组的成员对于这个文件具有，可读可写可执行的权限      
类似于windows中的组权限比如administrators组，属于这个组的成员对于文件的都有 可读可写可执行权限
 
第四段  --- 是指其他人对于这个文件没有任何权限
```

------

