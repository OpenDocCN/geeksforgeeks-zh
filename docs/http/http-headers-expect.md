# HTTP 头|期望

> 原文:[https://www.geeksforgeeks.org/http-headers-expect/](https://www.geeksforgeeks.org/http-headers-expect/)

**HTTP 头期望**请求头字段用于指示服务器为了响应客户端而需要满足的特定行为或期望。通常，**期望:***100-继续*是为表头字段定义的唯一期望。如果报头字段中提供的数据满足期望值，则服务器以 100 响应，表示成功，否则以状态 **417** 响应，指定期望值失败。放置 Expect 的原因是为了解决网络服务器损坏的问题。

**语法:**

```html
Expect: 100-continue
```

**指令:**

*   **100-Continue:** indicates that the server has received the request header, and in order to send the request body, the server must respond to the client in a state of 100.

**注意:**如果不打算放任何 Expect 子句，就不需要放空白的表头。

**例:**

```html
PUT /demo/program HTTP/1.1
Host: original.sample.com
Content-Type: video/h264
Content-Length: 2342564178765
Expect: 100-continue
```

服务器现在检查请求标题，并以 **100** 作出响应，指示客户端发送请求正文，或者如果未满足期望，则返回状态 **417** 。

**支持的浏览器:**除了之外， **HTTP 头的浏览器兼容性目前未知。**