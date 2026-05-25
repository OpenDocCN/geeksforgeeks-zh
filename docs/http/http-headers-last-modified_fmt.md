# HTTP 头：Last-Modified

> 原文：[https://www.geeksforgeeks.org/http-headers-last-modified/](https://www.geeksforgeeks.org/http-headers-last-modified/)

`Last-Modified` 响应头是由服务器发送的头，它指定最后修改所请求资源的日期。这是 HTTP 头 `Last-Modified` 的正式定义，让我们把它分解一下。

假设您已经创建了一个网站并设置了上次修改的标题。当用户浏览您的网站时，用户的浏览器会临时存储（缓存）一些信息，如 HTML、图像、样式表，甚至一些不常更改的动态内容。默认情况下，所有浏览器总是缓存资源，因此不需要特殊的头响应。

现在用户喜欢你的网站，再次访问！这次你比以前更好了。服务器将检查用户上次访问后您是否更新了网站。如果没有变化，服务器向浏览器发送 `304 Not Modified` 回复，信息从本地缓存加载。

`Last-Modified` 报头是与请求报头一起使用的响应报头，该请求报头称为 `If-Modified-Since` 头。`If-Modified-Since` 头向服务器发送一个请求，以了解资源上次被修改的时间。`Last-Modified` 头告诉浏览器上次修改资源的时间，以及它应该使用缓存的副本还是下载网站的更新版本。这些是缓存控制头。

## 语法

```html
Last-Modified: <day-name>, <day> <month> <year> <hour>:<minute>:<second> GMT
```

**注：** 上次修改的表头如下：`Last-Modified: Tue, 15 Oct 2019 12:45:26 GMT`

## 指令

*   `<day-name>`：包含“Mon”、“Tue”等日名。（区分大小写）。
*   `<day>`：包含 2 位数的日期，如“04”或“23”表示日。
*   `<month>`：包含月份的名称，以 3 个字母表示的月份名称如“Jan”、“Feb”等。（区分大小写）。
*   `<year>`：包含“2009”这样的 4 位数年份。
*   `<hour>`：包含 2 位数小时，如“07”或“12”。
*   `<minute>`：与小时分钟相同 2 位数分钟如“09”或“55”。
*   `<second>`：包含 2 位数秒的秒，如“08”或“50”。
*   `GMT`：HTTP 中的所有日期将以格林威治标准时间格式显示，而不是以当地时间格式显示。

## 示例

```html
Last-Modified: Tue, 15 Oct 2019 12:45:26 GMT
```

## 优势

*   这减少了带宽的使用，提高了网站的速度。
*   减少服务器上的负载。

要检查上次修改的运行情况，请转到“检查元素 -> 网络”检查 `Last-Modified` 的请求头，如下所示，`Last-Modified` 突出显示。

## 支持的浏览器

`Last-Modified` HTTP 头支持的浏览器如下：

*   Google Chrome
*   Microsoft Edge
*   Firefox
*   Safari
*   Opera