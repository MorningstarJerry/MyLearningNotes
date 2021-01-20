# 本地配置
C:\Program Files\MySQL\MySQL Server 5.6

https://downloads.mysql.com/archives/installer/

```
choco install mysql -y

root
Jabil@123
```
```
mysql -u root -p
```

![image-20210105101825909](C:\Users\2294765\AppData\Roaming\Typora\typora-user-images\image-20210105101825909.png)

`update user set password=password("Jabil@123") where user="pUser";`

![image-20210105101848707](C:\Users\2294765\AppData\Roaming\Typora\typora-user-images\image-20210105101848707.png)

`flush privileges;`

![image-20210105101954596](C:\Users\2294765\AppData\Roaming\Typora\typora-user-images\image-20210105101954596.png)