# HTTP 头| Cookie2

> 原文:[https://www.geeksforgeeks.org/http-headers-cookie2/](https://www.geeksforgeeks.org/http-headers-cookie2/)

**HTTP 头 Cookie2** 头是请求类型头，它被用来通知服务器用户代理理解**“新风格”**Cookie，但是这一天这个头不再使用而是使用 **[HTTP 头 Cookie](https://www.geeksforgeeks.org/http-headers-cookie/) 。**

**语法:**

```html
Cookie2: <cookie-list>
```

在单一 cookie 的情况下，语法如下:

```html
Cookie2: $Version="3"
```

在多个 cookies 的情况下，语法如下:

```html
Cookie2: name=value; name=value; name=value
```

**指令:**该标题接受上面提到的和下面描述的单个指令:

*   **< cookie-list > :** 它是名称=值对的列表，用；和空间，即“；”。

**例:**

```html
Cookie2: $Version="3"
```

**注意:**这几天没有使用这个表头。所以现在没有使用这个标题，所以无法管理实例。

**支持的浏览器:**浏览器与 **HTTP 头 Cookie2** 不兼容。 **HTTP 头 Cookie 2**被 [HTTP 头 Cookie](https://www.geeksforgeeks.org/http-headers-cookie/) 取代。