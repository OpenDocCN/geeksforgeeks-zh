# HTTP 头|代理-授权

> 原文:[https://www . geesforgeks . org/http-headers-proxy-authorization/](https://www.geeksforgeeks.org/http-headers-proxy-authorization/)

**HTTP Proxy_Authorization** 头是一种请求类型的头。此标头包含在用户代理和用户指定的服务器之间进行身份验证的凭据。当服务器响应 407“需要代理身份验证”状态时，将在用户代理和服务器之间进行身份验证。

**语法:**

```html
Proxy-Authorization: <type> <credentials>
```

**指令:**该表头接受两个指令，如上所述，描述如下:

*   **< Type >:** This instruction describes the type of certification. The common type of is Basic.
*   **< Voucher >:** This is the result string encoded by base64\. Credentials constructed like username and password are combined with colons like (username: password).

**例:**

```html
Proxy-Authorization: Basic 6dc7dbfe151046f2be8fc383a9abb147
```

此示例具有代理授权，其类型为基本，凭据如上。

要检查代理授权是否有效，请转到**检查元素- >网络**检查代理授权的请求头。

**支持的浏览器**与 **HTTP 代理-授权**头兼容的浏览器如下: