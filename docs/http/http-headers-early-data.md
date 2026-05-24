# HTTP 头|早期数据

> 原文:[https://www.geeksforgeeks.org/http-headers-early-data/](https://www.geeksforgeeks.org/http-headers-early-data/)

**早期数据**头是一种允许客户端立即发送请求的 HTTP 头。这确保了不存在传输层安全性(TLS)握手执行所需的一个或两个往返延迟。当该报头被设置时，它指示请求已经由中间代理在 TLS 早期数据中传送。它还表明中间代理已经理解了 425(过早)状态代码。

**语法:**

```html
Early-Data: 1
```

**注:**此处早-数据已设置(1)。

**指令:**该表头不接受任何指令。

**例:**

```html
GET /resource HTTP/1.0
Host: www.geeksforgeeks.org
Early-Data: 1
```

**支持的浏览器:**支持的浏览器有 **HTTP 早期数据头**列表如下: