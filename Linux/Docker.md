# Docker Install

https://docs.docker.com/engine/install/

# Docker Hub 
https://hub.docker.com/_/microsoft-dotnet-aspnet/

# Dockerfile reference
https://docs.docker.com/engine/reference/builder/

# Docker 本地文档打开
`
docker run  -it -p 4000:4000 docs/docker.github.io:v1.9
http://127.0.0.1:4000/v1.9/engine/misc/deprecated/
`
![image-20201227222344475](C:\Users\2294765\AppData\Roaming\Typora\typora-user-images\image-20201227222344475.png)

# Docker 常用命令
```
#查看当前的镜像
docker images

查看当前运行的容器
==========================
docker ps
docker ps -a

运行当前镜像
================
docker run myfirstmvccontainer

停止镜像运行起来后的默认容器名
============================
docker stop  wonderful_saha

启动停止的容器
==========================
docker start wonderful_saha

删除当前容器
================
docker rm -f wonderful_saha

启动容器 并做端口映射
================
docker run -p 8011:80 --name mvc1 -d  myfirstmvccontainer

删除镜像
=================
docker rmi jerrydanks

镜像复制打 tag 映射到dockerhub resp
=================
docker tag myfirstnet5mvcapp jerrydanks/firstmvc:netcore3mvc

推送到docker hub 
===============================
docker push jerrydanks/firstmvc:netcore3mvc
```

# 本地编译打包 Image

在包含dockerfile 的目录下生成镜像 myfirstmvccontainer
`docker build --tag myfirstmvccontainer . `


# Docker 发布并运行在实际环境

## 创建 Docker Hub 仓库

![image-20201225144738895](C:\Users\2294765\AppData\Roaming\Typora\typora-user-images\image-20201225144738895.png)

## 开发机打包镜像 映射远程 并推送到 docker Hub
```
docker tag myfirstnet5mvcapp jerrydanks/mynet5_core_app:Net5mvc1
docker push jerrydanks/mynet5_core_app:Net5mvc1
```

## 在远程云 CentOS 中下载镜像， 查看镜像
```
[root@NET5CentOS8 tmp]# docker pull jerrydanks/mynet5_core_app:Net5mvc1
[root@NET5CentOS8 tmp]# docker images
```

![image-20201225145134614](C:\Users\2294765\AppData\Roaming\Typora\typora-user-images\image-20201225145134614.png)

## 远程服务器运行容器
```
[root@NET5CentOS8 tmp]# docker run -p 8888:80 --name mvc1 -d  3c7eb8c16cd8
0096ea8508c6f690ced5f5b1b7de43336c1f10f833595534694094a400416b5a
[root@NET5CentOS8 tmp]# docker ps
CONTAINER ID   IMAGE          COMMAND                  CREATED         STATUS         PORTS                           NAMES
0096ea8508c6   3c7eb8c16cd8   "dotnet aspnetcoreMv…"   7 seconds ago   Up 5 seconds   443/tcp, 0.0.0.0:8888->80/tcp   mvc1
```


## 服务器上测试服务是否正常 curl
```
[root@NET5CentOS8 tmp]# CURL -i http://localhost:8888
-bash: CURL: command not found
[root@NET5CentOS8 tmp]# curl -I http://localhost:8888
HTTP/1.1 200 OK
Date: Fri, 25 Dec 2020 06:57:06 GMT
Content-Type: text/html; charset=utf-8
Server: Kestrel
```

## 浏览器中进行访问地址
```
http://47.115.181.225:8888/
```

![image-20201225150254559](C:\Users\2294765\AppData\Roaming\Typora\typora-user-images\image-20201225150254559.png)

## ASPNET Core runtimes on docker
https://hub.docker.com/_/microsoft-dotnet-aspnet/

![image-20201228095336435](C:\Users\2294765\AppData\Roaming\Typora\typora-user-images\image-20201228095336435.png)