# DDD Doman Driven Design 

## 域模型层(Ordering.Domain)
```
负责表示业务概念、有关业务状况的信息和业务规则。 反映业务状况的状态是通过这个层进行控制和利用的，但有关状态存储的具体技术细节则由基础结构负责实施。 这一层是业务软件的核心。
```
## 应用程序层(Ordering.API)
```
定义软件要完成的作业并指导富有表现力的域对象解决问题。 这一层负责执行对业务具有意义的任务或与其他系统的应用层进行交互时需执行的任务。 这一层很“薄”。 它不包含业务规则或知识，仅针对下一层中域对象之间的协作，协调任务和委派工作。 它不具有反映业务状况的状态，但它可以具有状态，用于反映用户或程序的任务的进度。
```

## 基础结构层(Ordering.Infrastructure)
```
基础结构层是关于如何将最初存放在域实体中的数据（内存中）持久保存在数据库或另一个持久性存储区中。 一个例子是使用 Entity Framework Core 代码实现存储库模式类，该类使用 DBContext 将数据持久保存在关系数据库中。
```

![image-20201231130408077](C:\Users\2294765\AppData\Roaming\Typora\typora-user-images\image-20201231130408077.png)

# Sample

https://github.com/dotnet-architecture/eShopOnContainers

`C:\Users\2294765\source\repos\DDDMicroService\eShopOnContainers-dev`

![image-20210105120135788](C:\Users\2294765\AppData\Roaming\Typora\typora-user-images\image-20210105120135788.png)

