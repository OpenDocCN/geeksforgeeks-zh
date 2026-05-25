# HTTP Trailer头

> 原文: [https://www.geeksforgeeks.org/http-headers-trailer/](https://www.geeksforgeeks.org/http-headers-trailer/)

`Trailer`是一个响应头，指示给定的一组头部字段出现在用分块传输编码编码的消息尾部，并允许发送方在分块消息的末尾包括附加字段，以便提供元数据。

## 语法

```html
Trailer: header-names
```

## 指令

*   `Header Name`：这是一组出现在用分块传输编码编码的消息末尾的头部字段。

## 示例

*   在此示例中，使用的头是`Max-Forwards`，它是一个请求修饰符。

```html
Trailer: Max-Forwards
```

*   在此示例中，使用的头是`Host`头，它是一个路由头。

```html
Trailer: Host
```

*   在此示例中，预告片头包含来自数据库查询的大量数据，这是一个分块响应。在此示例中，使用了`Expires`头。

```html
HTTP/1.0 200 OK 
Content-Type: text/plain 
Transfer-Encoding: chunked
Trailer: Expires

0\r\n
Mozilla\r\n 
7\r\n
Developer\r\n
9\r\n
Network\r\n
0\r\n 
\r\n
```

## 支持的浏览器

与`Trailer`头兼容的浏览器如下：