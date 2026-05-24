# HTTP 头|授权

> 原文:[https://www.geeksforgeeks.org/http-headers-authorization/](https://www.geeksforgeeks.org/http-headers-authorization/)

**HTTP 头授权**头是一个请求类型头，用于包含通过服务器验证用户的凭证信息。如果服务器以 **401 未授权**和 **WWW-Authenticate** 标头响应，通常不会。

**语法:**

```html
Authorization: <type> <credentials>
```

**指令:**本标题接受两个指令，如上所述，如下所述:

*   **< Type >:** The default authentication type saved in this instruction is **Basic** , and the other types are **iana registration authentication scheme** and [T6】 AWS server authentication (AWS 4-HMAC-SHA256)
*   **< Voucher >:** This instruction depends entirely on the type of authentication. If the authentication is basic, the structure of the certificate is the combination of user name and password and colon, such as **"User name: password"** , and the result string is base64 encoded.

**例:**

*   ```html
    Authorization: Basic YWxhZGRpbjpvcGVuc2VzYW1l
    ```

**支持的浏览器:**与 **HTTP 头授权**兼容的浏览器如下: