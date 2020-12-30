# 0.Dotnet5 

## 微服务 & DDD
https://docs.microsoft.com/zh-cn/dotnet/architecture/microservices/

## 数百万开发人员在使用或使用过 ASP.NET 4.x 创建 Web 应用。 ASP.NET Core 是对 ASP.NET 4.x 的重新设计，其中包括体系结构上的更改，产生了更精简、更模块化的框架.  


## ASP.NET Core 具有如下优点：
#### 1.生成 Web UI 和 Web API 的统一场景。
#### 2.针对可测试性进行构建。
#### 3.Razor Pages 可以使基于页面的编码方式更简单高效。
#### 4.Blazor 允许你在浏览器中使用 C# 和 JavaScript。 共享全部使用 .NET 编写的服务器端和客户端应用逻辑。
#### 5.能够在 Windows、macOS 和 Linux 上进行开发和运行。
#### 6.开放源代码和以社区为中心。
#### 7.集成新式客户端框架和开发工作流。
#### 8.支持使用 gRPC 托管远程过程调用 (RPC)。
#### 9.基于环境的云就绪配置系统。
#### 10.内置依赖项注入。
#### 11轻型的高性能模块化 HTTP 请求管道,能够托管于以下各项：
    #### Kestrel
    #### IIS
    #### HTTP.sys
    #### Nginx
    #### Apache
    #### Docker
    #### 并行版本控制。
    #### 简化新式 Web 开发的工具。


```
[访问示例]https://localhost:5001/api/MyNet5Test/8
        [HttpGet("{index}")]
        [ProducesResponseType(StatusCodes.Status200OK)]
        [ProducesResponseType(StatusCodes.Status404NotFound)]
        public IActionResult GetById(int index)
        {
       var methodsName = System.Reflection.MethodBase.GetCurrentMethod().Name;
            _logger.LogInformation($"exec method {methodsName}");
            List<TodoItem> lst = new List<TodoItem>();
            for (int i = 0; i < 5; i++)
            {
                TodoItem model = new TodoItem();
                model.Id = i;
                model.Name = $"Name{i.ToString()}";
                model.IsComplete = true;
                lst.Add(model);
            }

            if (lst.Find(p => p.Id.Equals(index)) != null)
            {
                _logger.LogInformation($"get index {index}");
                return Ok(lst);
            }
    
            _logger.LogInformation($"Not found");
            return NotFound();
        }
```

## Dotnet Try Tools

##  https://github.com/dotnet/try/blob/main/DotNetTryLocal.md



![image-20201228094354433](C:\Users\2294765\AppData\Roaming\Typora\typora-user-images\image-20201228094354433.png)



![image-20201228094554756](C:\Users\2294765\AppData\Roaming\Typora\typora-user-images\image-20201228094554756.png)

