# HTTP头 | Sec-WebSocket-Accept

> 原文: [https://www.geeksforgeeks.org/http-headers-sec-websocket-accept/](https://www.geeksforgeeks.org/http-headers-sec-websocket-accept/)

**HTTP头**用于在客户端和服务器之间通过HTTP请求或响应传递附加信息。它们被分组为*通用头、请求头、响应头、实体头*。`Sec-WebSocket-Accept`报头属于响应类型报头类别。服务器使用它来告知客户端它理解了什么。这是一个网络套接字连接，它准备打开连接。这对反向代理服务器来说很方便，因为它可以理解网络套接字握手，并且不会产生无用的缓存。`Sec-WebSocket-Accept`标头在HTTP响应中不能出现多次。

**注意:** HTTP头通常包含不区分大小写的名称，后跟冒号(`:`)，然后是其值。此处忽略值前的空白。

## 语法

```html
Sec-WebSocket-Accept: <hashed key>
```

## 指令

HTTP `Sec-WebSocket-Accept`头接受上面提到的、下面描述的单个指令:

*   `<SHA-1 key>` The server acquires the value of `Sec-WebSocket-Key` sent in the handshake request, and then adds `globally unique identifier (GUID, [RFC 4122]) "258EAF5-E914-47DA-95CA-C5AB0DC85B11"` to acquire.

下面的例子将说明 **HTTP Sec-WebSocket-Accept头**:

## 示例

在此示例中，如果传入的连接是到客户端的WebSocket连接，服务器将发送101个响应代码。

```html
101 Switching Protocols
Upgrade: websocket
Connection: Upgrade
Sec-WebSocket-Accept: MTMyNThFQUZBNS1FOTE0LTQ3REEtOTVDQS1DNUFCMERDODVCMTE=
Sec-WebSocket-Extensions: deflate-frame
Sec-WebSocket-Protocol: soap
```

## 注意

这个标题不稳定，目前很少有关于这个标题的研究。

## 支持的浏览器

浏览器兼容HTTP `Sec-WebSocket-Accept` header列表如下: