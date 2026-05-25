# HTTP 头：Upgrade-Insecure-Requests

> 原文：[https://www.geeksforgeeks.org/http-headers-upgrade-insecure-requests/](https://www.geeksforgeeks.org/http-headers-upgrade-insecure-requests/)

`Upgrade-Insecure-Requests` 是一个请求类型头。它向服务器发送一个信号，表达客户端对加密和认证响应的偏好，它可以成功处理升级不安全请求 `Content-Security-Policy` 指令。

## 语法

```
Upgrade-Insecure-Requests: 1
```

## 指令

`Upgrade-Insecure-Requests` 头不接受任何指令。它充当带有一些标题的指令，例如用于处理 CSP 的 `Content-Security-Policy`。对于 `Vary` 头，它作为一个包含值 `1` 的指令工作。

## 示例

*   客户端请求向支持升级不安全请求升级机制的服务器发出信号：

```
GET / HTTP/1.0
Host: geeksforgeeks.org
Upgrade-Insecure-Requests: 1
```

*   服务器现在可以重定向到网站的安全版本。可以使用 `Vary` 头，这样该站点就不会被缓存提供给不支持升级机制的客户端：

```
Location: https://www.geeksforgeeks.org
Vary: Upgrade-Insecure-Requests
```

要检查此 `Upgrade-Insecure-Requests` 的执行情况，请转到 `检查元素 -> 网络` 检查 `Upgrade-Insecure-Requests` 的请求头，如下所示，`Upgrade-Insecure-Requests` 突出显示，您可以看到。

## 支持的浏览器

浏览器兼容 `Upgrade-Insecure-Requests` 标题如下：

*   谷歌 Chrome
*   微软边缘
*   火狐浏览器
*   歌剧
*   旅行队