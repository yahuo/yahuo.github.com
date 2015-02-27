---
layout:     post
title:      "docker学习笔记(持续更新)"
date:       2015-02-27 16:23:00
categories: online
author:     "金鑫"
header-img: "img/post-bg-02.jpg"
---

## 进入镜像，命令行交互

```bash
docker run -i -t ubuntu:14.04.1 /bin/bash
```
`-i`:表示以“交互模式”运行容器

`-t`:表示容器启动后会进入其命令行

`-v`:表示需要将本地哪个目录挂载到容器中，格式：-v <宿主机目录>:<容器目录>

## 删除容器或镜像

```bash
docker rm <containerID>       #删除指定容器
docker rm `docker ps -a -q`   #删除所有容器
docker rmi <imageID>          #删除镜像
```

## 通过ssh连接镜像

### 映射端口访问

```bash
docker run -d -p 22 <imageID> /usr/sbin/sshd -D
```
> `-p 22 `后面加上`-p 80:8080`映射tomcat端口

### 登录ssh

```bash
ssh root@127.0.0.1 -p #映射端口
```

### 配置jdk

```bash
#解压jdk到`/usr/java/`,在`~/.bashrc`中配置环境变量
export JAVA_HOME=/usr/java/jdk1.7.0_40
export PATH=$PATH:$JAVA_HOME/bin
source /etc/profile
```

## 提交

```bash
docker commit <containerID>   #提交容器
docker push <imageID>:<TAG>   #提交到仓库
```

### 参考

- http://my.oschina.net/huangyong/blog/372491
