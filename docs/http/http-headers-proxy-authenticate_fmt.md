# HTTP 头：代理-认证

> 原文：[https://www.geeksforgeeks.org/http-headers-proxy-authenticate/](https://www.geeksforgeeks.org/http-headers-proxy-authenticate/)

`HTTP 代理认证`是一个响应头，通过定义授权方法来访问资源文件。它允许代理服务器通过验证它来进一步传输请求。此标头与 407“需要代理身份验证”一起发送，表示由于拦截请求的代理服务器缺乏适当的授权凭据，无法完成请求。

## 语法

```
Proxy-Authenticate:<type> realm=<realm>
```

## 指令

*   `<type>`：此值仅为一种认证类型。
*   `realm=<realm>`：此值用于描述受保护区域或范围。如果未指定 `realm`，则将显示格式化的主机名。

## 例

```
Proxy-Authenticate: Basic
```

基本身份验证类型接受用户名和密码来验证身份验证。

```
Proxy-Authenticate: Basic realm="Access to Geeksforgeeks website"
```

这使得在接受用户名和密码后可以访问极客网站。

## 支持的浏览器

以下浏览器兼容 `HTTP 代理-认证头`：