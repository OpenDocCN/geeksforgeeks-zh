# HTTP 头|原点

> 原文:[https://www.geeksforgeeks.org/http-headers-origin/](https://www.geeksforgeeks.org/http-headers-origin/)

**源 HTTP 头**是一个响应 HTTP 头，指示启动 HTTP 请求的安全上下文，而不指示路径信息。原点标题是由浏览器添加的，用户无法控制。

**语法:**

```html
Origin: <scheme> "://" <hostname> ":" <port> 
```

**指令:**

*   <scheme>:

    这通常是使用的 HTTP 或 HTTPS 协议。

*   <hostname>:

    这是服务器的 IP 或域名。

*   <port>:

    这是一个可选指令，告知服务器的传输控制协议端口号。如果未指定默认端口，则默认端口是隐含的。

**示例:**

```html
Origin: null
```

这意味着所请求的服务没有来源。

```html
Origin: https://www.geeksforgeeks.org
```

这意味着所请求的服务的来源存在，并且以 https 作为方案，以 www.geeksforgeeks.org 作为主机名。

**支持的浏览器**以下浏览器兼容 HTTP Origin:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   歌剧
*   火狐浏览器
*   旅行队