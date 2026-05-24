# HTTP | PUT

> 原文:[https://www.geeksforgeeks.org/http-put/](https://www.geeksforgeeks.org/http-put/)

**HTTP PUT 请求方法**用于创建一个新资源或覆盖客户端已知的目标资源的表示。调用此方法一次类似于连续调用多次，因为它具有相同的效果。虽然它是幂等的，但我们无法缓存它的响应。

**语法:**

```html
PUT /html file HTTP/1.1
```

**示例:**
**请求:**

```html
PUT /example.html HTTP/1.1
Host: sample.com
Content-type: text/html
Content-length: 20

<p>New File</p>
```

**响应:**如果 PUT 请求成功创建了新资源，那么服务器通过发送 201(Created)响应来通知用户。
T3】输出:

```html
HTTP/1.1 201 Created
Content-Location: /example.html
```

如果目标资源已经有一个表示，并且它被请求成功修改，那么服务器必须发送 200(正常)或 204(无内容)响应，指示响应成功。
**输出:**

```html
HTTP/1.1 204 No Content
Content-Location: /newexample.html 
```

**支持的浏览器:****HTTP | PUT**支持的浏览器如下:

*   谷歌 Chrome 6.0+
*   Internet Explorer 9.0+
*   Firefox 4.0+
*   苹果 Safari 5.0
*   歌剧 11.1