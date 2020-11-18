---
title: docker
categories: Docker
tags: level V
date: 2020-11-16 16:07:54
---

### Docker

#### 常用命令

```
# 在docker反复build后，会存留很多none镜像，下面命令一键删除所有none镜像
docker rmi `docker images | grep  '<none>' | awk '{print $3}'`
或者
docker rmi $(docker images -q -f dangling=true)
# 删除所有停止的容器
docker rm $(docker ps -a -q)
```

#### 删除所有未运行的容器

```
docker rm $(docker ps -a -q)
```

##### docker cp

```
# 将主机/www/runoob目录拷贝到容器96f7f14e99ab的/www目录下。
docker cp /www/runoob 96f7f14e99ab:/www/
# 将主机/www/runoob目录拷贝到容器96f7f14e99ab中，目录重命名为www。
docker cp /www/runoob 96f7f14e99ab:/www
# 将容器96f7f14e99ab的/www目录拷贝到主机的/tmp目录中。
docker cp  96f7f14e99ab:/www /tmp/
```

#### 基础知识

##### 概念

- 镜像 Image
- 容器 Container，镜像的一个实例
- 仓库 Repository，用来存储镜像

##### 容器使用-常用命令及参数

*运行容器命令 docker run*

```
# 命令 docker run
-i 标准输入，进行交互
-t 指定伪终端
-d 运行模式，后台运行
-P 将容器内部使用的网络端口随机映射到我们使用的主机上
-p 指定映射的端口
# 例子
docker run -i -t ubuntu:15.10 /bin/bash
docker run ubuntu:15.10 /bin/echo "Hello world"
docker run -d -p [127.0.0.1:]5000:5000[/udp] training/webapp python app.py
```

*进入容器命令 docker exec*

```
# 命令 docker exec
docker exec -it container_id /bin/bash  # 退出不会停止容器
docker attach container_id  # 退出会停止容器
# 退出容器
exit
```

*查看容器的命令 docker ps*

```
# 命令 docker ps
默认查看正在运行的容器
-a 查看所有容器
-l 查看最后一次创建的容器
```

*其他命令*

```
# 查看容器的标准输出  -f 让 docker logs 像使用 tail -f 一样来输出容器内部的标准输出。
docker logs container_id
# 运行容器
docker start container_id
# 停止容器
docker stop container_id
# 重启容器
docker restart container_id
# 获取容器
docker pull ubuntu
# 删除容器
docker rm -f container_id
# 导出容器
docker export container_id > ubuntu.tar
# 导入容器
cat docker/ubuntu.tar | docker import - test/ubuntu:v1
# 通过url来导入
docker import http://example.com/exampleimage.tgz example/imagerepo
# 查看容器端口映射情况
docker port container_id
# 容器命名
docker run -d -P --name mingzi training/webapp python app.py
```

##### 镜像使用-常用命令及参数

```
# 查看已有镜像
docker images
# 在网络中搜索镜像
docker search python3
# 下载镜像
docker pull python3
# 删除镜像
docker rmi hello-world
# --更新镜像--
docker run -t -i ubuntu:15.10 /bin/bash # 运行一个容器
在运行的容器内使用 apt-get update 命令进行更新。
在完成操作之后，输入 exit 命令来退出这个容器。
此时 ID 为 e218edb10161 的容器，是按我们的需求更改的容器。通过命令docker commit来提交容器副本。
docker commit -m="has update" -a="zuozhe" e218edb10161 runoob/ubuntu:v2
# --使用Dockerfile文件来创建镜像--， -t指定创建的目标镜像名
docker build -t runoob/centos:biaoqian .  # 点好表示Dockerfile文件所在目录
# 设置镜像标签
docker tag image_id runoob/centos:dev
```

##### Docker 容器连接

*网络端口映射*

```
docker run -d -P training/webapp python app.py
docker run -d -p 5000:5000 training/webapp python app.py
docker run -d -p 127.0.0.1:5001:5000 training/webapp python app.py
docker run -d -p 127.0.0.1:5000:5000/udp training/webapp python app.py
```

*容器互联*

```
# 新建网络
docker network create -d bridge test-net 
# 查询网络
docker network ls
# 运行一个容器并连接到新建的 test-net 网络
docker run -itd --name test1 --network test-net ubuntu /bin/bash 
docker run -itd --name test2 --network test-net ubuntu /bin/bash
```

##### Docker 仓库管理

#####  Docker Dockerfile

*例子 - 创建一个Dockerfile文件，内容如下：*

```
FROM nginx
RUN echo '这是一个本地构建的nginx镜像' > /usr/share/nginx/html/index.html
COPY hom?.txt /mydir/
# ADD
# CMD
```

```
# 构造命令
docker build -t nginx:v3 .
&&
```

```shell
# 常用命令
RUN <命令行命令>   # 多个命令，以 && 符号连接命令
COPY [--chown=<user>:<group>] <源路径1>...  <目标路径>
ADD # ADD 指令和 COPY 的使用格式一致,官方推荐使用 COPY
CMD ["<可执行文件或命令>","<param1>","<param2>",...]  # CMD 在docker run 时运行。
ENTRYPOINT ["<executeable>","<param1>","<param2>",...]
# 环境变量
ENV <key> <value>
ENV <key1>=<value1> <key2>=<value2>...
ARG <参数名>[=<默认值>]  # 仅 docker build 的过程中有效
# 匿名数据卷
VOLUME <路径>
WORKDIR <工作目录路径>
USER <用户名>[:<用户组>]
```



