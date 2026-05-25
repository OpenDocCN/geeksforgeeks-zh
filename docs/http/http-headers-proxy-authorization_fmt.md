# HTTP 头：代理授权

> 原文：[https://www.geeksforgeeks.org/http-headers-proxy-authorization/](https://www.geeksforgeeks.org/http-headers-proxy-authorization/)

`Proxy-Authorization` 头是一种请求类型的头。此标头包含在用户代理和用户指定的服务器之间进行身份验证的凭据。当服务器响应 407“需要代理身份验证”状态时，将在用户代理和服务器之间进行身份验证。

## 语法

```
Proxy-Authorization: <type> <credentials>
```

## 指令

该表头接受两个指令，如上所述，描述如下：

*   `<type>`：此指令描述认证的类型。常见类型是 `Basic`。
*   `<credentials>`：这是由 base64 编码的结果字符串。凭据（如用户名和密码）组合时用冒号分隔，例如 `(username:password)`。

## 例

```
Proxy-Authorization: Basic 6dc7dbfe151046f2be8fc383a9abb147
```

此示例具有代理授权，其类型为基本，凭据如上。

要检查代理授权是否有效，请转到`检查元素->网络`检查代理授权的请求头。

## 支持的浏览器

与 `Proxy-Authorization` 头兼容的浏览器如下：