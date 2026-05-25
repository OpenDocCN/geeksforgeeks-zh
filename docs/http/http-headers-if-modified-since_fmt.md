# HTTP 头 | If-Modified-Since

> 原文: [https://www.geeksforgeeks.org/http-headers-if-modified-since/](https://www.geeksforgeeks.org/http-headers-if-modified-since/)

`If-Modified-Since`头是作为条件请求发送到服务器的请求头。如果内容发生了变化，服务器会以 200 状态码进行响应，并更新整个请求的文档。`If-Modified-Since` HTTP 头指示浏览器第一次从服务器下载资源的时间。这有助于确定自上次访问以来资源是否已更改。如果特定资源的状态为 304“未修改”，这意味着文件没有更改，不需要再次下载。

让我们以这个网站为例，它有不同的关于计算机科学主题的页面。每当搜索引擎访问这个网站时，它将检查网站的每个页面，如果没有页面发生变化，它将不会加载任何这些页面。但是如果它的任何一页有变化，就会升起一面旗帜。因此，当搜索引擎访问时，它将看到已更改页面的标志，然后它将访问该页面。

**注意:** 与 `If-Unmodified-Since` 结合使用时，将被忽略，除非服务器不支持 `If-Unmodified-Since`。

**语法:**

```
If-Modified-Since: <day-name>, <day> <month> <year> <hour>:<minute>:<second> GMT
```

**指令:** 该标题接受八个指令，如上所述，如下所述:

*   `<day-name>`: 包含“Mon”、“Tue”等日名。(区分大小写)。
*   `<day>`: 它包含 2 位数的日期，像“04”或“23”代表天。
*   `<month>`: 包含月份的名称，以 3 个字母表示的月份名称如“Jan”、“Feb”等。(区分大小写)。
*   `<year>`: 包含“2020”这样的 4 位数年份。
*   `<hour>`: 包含 2 位数小时，如“07”或“12”。
*   `<minute>`: 与小时分钟相同 2 位数分钟如“09”或“55”。
*   `<second>`: 包含 2 位数秒的秒，如“08”或“50”。
*   `GMT`: HTTP 中的所有日期将以格林威治标准时间格式显示，而不是以当地时间格式显示。

**示例:**

```
If-Modified-Since: Sun, 10 May 2020 02:01:00 GMT
```

**支持的浏览器:** 支持的浏览器 `If-Modified-Since` 头如下:

*   Google Chrome
*   Firefox
*   Microsoft Edge
*   Opera
*   Safari