# CentOS 启动NetCore5
```
dotnet MyNet5APIs.dll
dotnet MyNet5APIs.dll --urls=http://*:8888
```

## 解决服务器上端口无法监听的问题
```
dotnet MyNet5APIs.dll --urls "http://*:5000;https://*:5001"
https://47.115.181.225:5001/swagger/index.html
```

## 远程访问地址
```
https://47.115.181.225:5001/api/MyNet5Test
https://47.115.181.225:5001/swagger/index.html
```

## 解决Nginx Swagger 无法访问的问题
```
server {
    listen        80;
    server_name   example.com *.example.com;
    location / {
        proxy_pass         http://localhost:5000;
        proxy_http_version 1.1;
        proxy_set_header   Upgrade $http_upgrade;
        proxy_set_header   Connection keep-alive;
        proxy_set_header   Host $host;
        proxy_cache_bypass $http_upgrade;
        proxy_set_header   X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header   X-Forwarded-Proto $scheme;
    }
}
```

```
using Microsoft.AspNetCore.HttpOverrides;

app.UseForwardedHeaders(new ForwardedHeadersOptions
{
    ForwardedHeaders = ForwardedHeaders.XForwardedFor | ForwardedHeaders.XForwardedProto
});

app.UseAuthentication();
```

![image-20201225121132846](C:\Users\2294765\AppData\Roaming\Typora\typora-user-images\image-20201225121132846.png)

## ASP.NET Core中配置监听URLs的五种方式

`https://www.cnblogs.com/lwqlun/p/12727098.html`

## Ubuntu
`sudo lsb_release -a`