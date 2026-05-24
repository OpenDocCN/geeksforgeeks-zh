# HTTP 头|尾

> 原文:[https://www.geeksforgeeks.org/http-headers-trailer/](https://www.geeksforgeeks.org/http-headers-trailer/)

**HTTP 尾部头**是一个响应头，指示给定的一组头部字段出现在用分块传输编码编码的消息尾部，并允许发送方在分块消息的末尾包括附加字段，以便提供元数据。

**语法:**

```html
Trailer: header-names
```

**指令:**

*   **Header Name:** This is a group of header fields that appear at the end of the message encoded by block transmission coding.

**示例:**

*   In this example, the header being used is maximum forwarding, which is a request modifier.

    ```html
    Trailer: Max-Forwards
    ```

*   In this example, the header being used is the [host](https://www.geeksforgeeks.org/http-headers-host/) header, which is the routing header.

    ```html
    Trailer: Host
    ```

*   In this example, the trailer head contains a large amount of data from the database query, which is a block response. In this example, the expired title is used.

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

**支持的浏览器:**与 **HTTP 预告片头**兼容的浏览器如下: