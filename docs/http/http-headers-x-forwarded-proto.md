# HTTP 头| X-转发-原型

> 原文:[https://www . geesforgeks . org/http-headers-x-forward-proto/](https://www.geeksforgeeks.org/http-headers-x-forwarded-proto/)

HTTP 头用于客户端和服务器之间的通信。HTTP 头允许客户端和服务器通过 HTTP 请求或响应传递附加信息。X-Forwarded-Proto (XPF)报头用于标识客户端用来连接代理或负载平衡器的协议。它可以是 HTTP 或 HTTPS。您的服务器访问日志通常包含有关服务器和负载平衡器之间使用的协议的信息，但不包含有关客户端和负载平衡器之间使用的协议的任何信息。为了获得关于客户端和负载均衡器之间使用哪种协议的信息，我们可以使用 **X-Forwarded-Proto** 请求头。使用这个头，客户端可以向一个仅 HTTPS 的资源发出一个 HTTP 请求。

**语法:**

```html
X-Forwarded-Proto: <protocol>

```

**指令:**

*   **< Protocol >:** This protocol contains the X-Forwarded-Proto request header (http or https) of the request from the client.

**示例 1:** 以下示例包含作为 HTTP 请求从客户端发出的请求的 X-Forwarded-Proto 请求头:

## HTML

```html
// X-Forwarded-Proto: originatingprotocol
X-Forwarded-Proto: http
```