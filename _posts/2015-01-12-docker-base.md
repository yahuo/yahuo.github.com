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
`-i`:表示以“交互模式”运行容器
`-t`:表示容器启动后会进入其命令行
`-v`:表示需要将本地哪个目录挂载到容器中，格式：-v <宿主机目录>:<容器目录>

#### 删除容器
```
docker rm #containerID
```

#### 删除所有容器
```
docker rm `docker ps -a -q`
```

#### 删除镜像
```
docker rmi #imageID
```

#### 后台运行ssh
```
docker run -d -p 22 #imageID /usr/sbin/sshd -D
```

> `-p 22 `后面加上-p 80:8080映射tomcat端口

#### 登录ssh
```
ssh root@127.0.0.1 -p #映射端口
```

#### 拷贝jdk到容器，配置解压jdk到`/usr/java/`，配置环境变量
```
vim ~/.bashrc
export JAVA_HOME=/usr/java/jdk1.7.0_40
export PATH=$PATH:$JAVA_HOME/bin
:wq
source /etc/profile
```

#### 提交容器，保存
```
docker commit #containerID
```

#### 提交镜像到仓库
```
docker push #imageID:<TAG>
```
