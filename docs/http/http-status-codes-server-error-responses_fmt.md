# HTTP 状态代码|服务器错误响应

> 原文: [https://www.geeksforgeeks.org/http-status-codes-server-error-responses/](https://www.geeksforgeeks.org/http-status-codes-server-error-responses/)

HTTP 状态代码是浏览器和站点服务器之间的对话。服务器以三位数代码的形式对浏览器的请求做出响应，称为 HTTP 状态代码。HTTP 状态代码的类别有：

*   信息回应 (100–199)
*   成功响应 (200–299)
*   重定向 (300–399)
*   客户端错误 (400–499)
*   服务器错误 (500–599)

## 服务器错误响应

服务器错误响应发生在服务器未能满足访问者的请求时。

### 500 内部服务器错误
`500` 内部服务器错误是一种常见的错误消息，当服务器遇到意外情况时，它不知道如何处理。

**状态:**
```html
500 Internal Server Error
```

### 501 未实现
`501` 未实现发生在服务器不支持请求的方法时。服务器要么没有察觉到请求，要么满足请求的能力不足。`GET` 和 `HEAD` 是服务器唯一支持的方法。

**状态:**
```html
501 Not Implemented
```

### 502 坏网关
`502` 坏网关发生在服务器作为网关工作时，它收到上游服务器的无效响应。

**状态:**
```html
502 Bad Gateway
```

### 503 服务不可用
`503` 服务不可用发生在服务器无法处理请求时（服务器暂时过载或停机）。

**状态:**
```html
503 Service Unavailable
```

### 504 网关超时
`504` 网关超时发生在服务器作为网关时，没有及时收到上游服务器的响应。

**状态:**
```html
504 Gateway Timeout
```

### 505 不支持的 HTTP 版本
`505` 不支持的 HTTP 版本发生在服务器不支持请求中使用的 HTTP 协议版本时。

**状态:**
```html
505 HTTP Version Not Supported
```

### 506 变体也协商
`506` 变体也协商发生在服务器出现内部配置错误时。

**状态:**
```html
506 Variant Also Negotiated
```

### 507 存储不足
`507` 存储不足发生在服务器由于操作规模大而无法存储或执行成功完成请求所需的（`PUT` 或 `POST`）操作时。

**状态:**
```html
507 Insufficient Storage
```

### 508 检测到循环
`508` 检测到循环发生在服务器在处理请求时检测到无限循环时。该请求被服务器终止。

**状态:**
```html
508 Loop Detected
```

### 510 未扩展
`510` 未扩展发生在服务器没有更多资源（扩展）来完成所需的请求时。

**状态:**
```html
510 Not Extended
```

### 511 Network Authentication Required
`511` Network Authentication Required 发生在访问者需要进行身份验证以获得网络访问权限时。

**状态:**
```html
511 Network Authentication Required
```

## 支持的浏览器
与 **HTTP 状态代码服务器错误响应** 兼容的浏览器如下：

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧