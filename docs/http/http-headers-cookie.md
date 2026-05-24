# HTTP 头| Cookie

> 原文:[https://www.geeksforgeeks.org/http-headers-cookie/](https://www.geeksforgeeks.org/http-headers-cookie/)

HTTP 头用于通过 HTTP 响应或 HTTP 请求传递附加信息。cookie 是一个 HTTP 请求头，即在用户发送给服务器的请求中使用。它包含服务器先前使用 *set-cookies* 发送的 cookies。这是一个可选的标题。

**语法:**

```html
Cookie: <cookie-list>
```

如果是单一 cookie，语法如下:

```html
Cookie: name=value
```

如果是多个 cookies，语法如下:

```html
Cookie: name=value; name=value; name=value
```

**指令:**该标题接受上面提到的和下面描述的单个指令:

*   **< cookie-list >** 是由**分隔的名称=值对的列表；**和空间即**；**。

**例 1:**

```html
Cookie: user=Bob
```

**例 2:**

```html
Cookie: user=Bob; age=28; csrftoken=u12t4o8tb9ee73
```

要检查该 Cookie 的运行情况，请转到**检查元素- >网络**检查 Cookie 的请求头，如下所示，Cookie 高亮显示，您可以看到。
T3】

**支持的浏览器:**支持的浏览器有 **HTTP Cookie 头**如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧