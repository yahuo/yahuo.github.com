---
layout:     post
title:      "docker学习笔记"
date:       2015-01-12 11:05:00
categories: online
author:     "金鑫"
header-img: "img/post-bg-02.jpg"
---

#### 进入镜像，命令行交互
```
docker run -i -t ubuntu:14.04.1 /bin/bash
```

#### 删除容器
```
docker rm container_id
```

#### 删除所有容器
```
docker rm `docker ps -a -q`
```

#### 删除镜像
```
docker rmi image_id
```

#### 容器运行结束，删除容器
```
docker run --rm=true image_id /bin/echo hello world
```

#### 后台运行ssh
```
docker run -d -p 22 image_id /usr/sbin/sshd -D
```

> `-p 22 `后面加上-p 80:8080映射tomcat端口

#### 登录ssh
```
ssh root@127.0.0.1 -p #映射端口
```

#### 拷贝jdk到容器，配置解压jdk到`/usr/java/`，配置环境变量
```
vim /etc/profile
JAVA_HOME=/usr/java/jdk1.7.0_40
CLASSPATH=.:$JAVA_HOME/lib/tools.jar
PATH=$JAVA_HOME/bin:$PATH
:wq
source /etc/profile
```

#### 提交容器，保存
```
docker commit #containerID
```
