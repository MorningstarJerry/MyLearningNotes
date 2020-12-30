# Linux 常用配置

## 教程
```
https://www.maxlist.xyz/2020/06/18/flask-nginx/#%E4%B8%80_%E5%AE%89%E8%A3%9D_Nginx
```
## 安装
`sudo yum install nginx`

## Nginx 版本查看

```
[root@NET5CentOS8 ~]# nginx -v
nginx version: nginx/1.14.1
[root@NET5CentOS8 ~]# nginx -h
nginx version: nginx/1.14.1
Usage: nginx [-?hvVtTq] [-s signal] [-c filename] [-p prefix] [-g directives]

Options:
  -?,-h         : this help
  -v            : show version and exit
  -V            : show version and configure options then exit
  -t            : test configuration and exit
  -T            : test configuration, dump it and exit
  -q            : suppress non-error messages during configuration testing
  -s signal     : send signal to a master process: stop, quit, reopen, reload
  -p prefix     : set prefix path (default: /usr/share/nginx/)
  -c filename   : set configuration file (default: /etc/nginx/nginx.conf)
  -g directives : set global directives out of configuration file


```

## 启动暂停重启
```
[root@NET5CentOS8 ~]# nginx
[root@NET5CentOS8 ~]# nginx -s stop
```

## 测试nginx 是否正常
```
[root@NET5CentOS8 /]# nginx -t
nginx: the configuration file /etc/nginx/nginx.conf syntax is ok
nginx: configuration file /etc/nginx/nginx.conf test is successful
```


## 配置文件
`[root@NET5CentOS8 ~]# vim /etc/nginx/nginx.conf

## 查看监听端口
```
[root@NET5CentOS8 ~]# netstat -antp
Active Internet connections (servers and established)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name    
tcp        0      0 0.0.0.0:5355            0.0.0.0:*               LISTEN      1029/systemd-resolv 
tcp        0      0 0.0.0.0:80              0.0.0.0:*               LISTEN      25575/nginx: master 
tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN      24588/sshd          
tcp        0      0 127.0.0.1:5000          0.0.0.0:*               LISTEN      25631/dotnet        
tcp        0      0 127.0.0.1:5001          0.0.0.0:*               LISTEN      25631/dotnet  
```

## 防火墙 how-to-configure-and-manage-firewall-on-centos-8

https://linuxize.com/post/how-to-configure-and-manage-firewall-on-centos-8/

```
systemctl start firewalld # 开启防火墙
systemctl stop firewalld	# 临时关闭防火墙命令。重启电脑后，防火墙自动起来。
systemctl disable firewalld  # 永久关闭防火墙命令。重启后，防火墙不会自动启动。
systemctl status firewalld # 查看firewalld状态。
```

```
查看防火墙某个端口是否开放
firewall-cmd --query-port=3306/tcp

开放防火墙端口3306
firewall-cmd --zone=public --add-port=3306/tcp --permanent

查看防火墙状态
systemctl status firewalld

关闭防火墙
systemctl stop firewalld

打开防火墙
systemctl start firewalld

开放一段端口
firewall-cmd --zone=public --add-port=40000-45000/tcp --permanent

查看开放的端口列表
firewall-cmd --zone=public --list-ports
```

# aliYun 上启动nginx 后外网无法访问

## 开启防火墙入站规则
https://blog.csdn.net/qq_22638399/article/details/81060535

![image-20201224162829832](C:\Users\2294765\AppData\Roaming\Typora\typora-user-images\image-20201224162829832.png)

再次访问成功

![image-20201224162747124](C:\Users\2294765\AppData\Roaming\Typora\typora-user-images\image-20201224162747124.png)

# Nginx 站点发布

### nginx 站点默认目录
` cd /usr/share/nginx/html`

### nginx 安装目录
`[root@NET5CentOS8 modules]# vim /etc/nginx/nginx.conf`
`[root@NET5CentOS8 modules]# cd  /etc/nginx/default.d`

###  nginx.config 
` root         /usr/share/nginx/html;`
change
` root         /usr/share/nginx/myapp/myapprelease;`