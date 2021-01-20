# 3.IndentityServer4

https://identityserver4.readthedocs.io/en/latest/index.html

https://www.cnblogs.com/stulzq/p/8119928.html

## Authentication + Authorization

### OpenID  (Authentication 认证) 是一个以用户为中心的数字身份识别框架，它具有开放、分散性。OpenID 的创建基于这样一个概念：我们可以通过 URI （又叫 URL 或网站地址）来认证一个网站的唯一身份，同理，我们也可以通过这种方式来作为用户的身份认证。

### OAuth（Authorization 开放授权）是一个开放标准，目前的版本是2.0。允许用户授权第三方移动应用访问他们存储在其他服务商上存储的私密的资源（如照片，视频，联系人列表），而无需将用户名和密码提供给第三方应用。

### OpenID Connect 1.0 是基于OAuth 2.0协议之上的简单身份层，它允许客户端根据授权服务器的认证结果最终确认终端用户的身份，以及获取基本的用户信息；它支持包括Web、移动、JavaScript在内的所有客户端类型去请求和接收终端用户信息和身份认证会话信息；它是可扩展的协议，允许你使用某些可选功能，如身份数据加密、OpenID提供商发现、会话管理等。

`OpenId Connect = OIDC = Authentication + Authorization + OAuth2.0`

## 认证模式 （HTTP身份验证流程 + JWT）

Json web token (JWT), 是为了在网络应用环境间传递声明而执行的一种基于JSON的开放标准（RFC 7519）。该token被设计为紧凑且安全的，特别适用于分布式站点的单点登录（SSO）场景。JWT的声明一般被用来在身份提供者和服务提供者间传递被认证的用户身份信息，以便于从资源服务器获取资源，也可以增加一些额外的其它业务逻辑所必须的声明信息，该token也可直接被用于认证，也可被加密。

* Header：由alg和typ组成，alg是algorithm的缩写，typ是type的缩写，指定token的类型。该部 分使用Base64Url编码。
* Payload：主要用来存储信息，包含各种声明，同样该部分也由BaseURL编码。
* Signature：签名，使用服务器端的密钥进行签名。以确保Token未被篡改。

```
HMACSHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),
  secret)
```
## OAuth2.0 定义了四种授权模式：

* 1.Implicit：简化模式；直接通过浏览器的链接跳转申请令牌。
* 2.Client Credentials：客户端凭证模式；该方法通常用于服务器之间的通讯；该模式仅发生在Client与Identity Server之间。
* 3.Resource Owner Password Credentials：密码模式。(终端用户到受保护的资源之间)
* 4.Authorization Code：授权码模式；

## IdentityServer4是为ASP.NET CORE量身定制的实现了OpenId Connect和OAuth2.0协议的认证授权中间件。

<img src="C:\Users\2294765\AppData\Roaming\Typora\typora-user-images\image-20201216110304560.png" alt="image-20201216110304560" style="zoom:50%;" />

# Get Start With IndentityServer 4
https://www.scottbrady91.com/Identity-Server/Getting-Started-with-IdentityServer-4

![image-20210111102442331](C:\Users\2294765\AppData\Roaming\Typora\typora-user-images\image-20210111102442331.png)

https://github.com/IdentityServer/IdentityServer4.Demo.git



https://www.cnblogs.com/Zing/p/13366318.html



