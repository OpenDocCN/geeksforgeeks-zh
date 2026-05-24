# ASP 请求。饼干收集

> 原文:[https://www . geesforgeks . org/ASP-request-cookies-collection/](https://www.geeksforgeeks.org/asp-request-cookies-collection/)

基本上，Cookies 是存储在用户计算机上的小文件。它们用于保存特定客户端和网站的少量数据，可以由网络服务器或客户端计算机访问。

**请求。饼干集合**用于返回饼干集合的值。如果指定的 cookie 不存在，则会创建它。如果 cookie 存在，它将接受新值，旧值将被丢弃。

**语法:**

```vb
Request.Cookies( cookie )[(key)|**.**attribute]
```

**参数:**

*   **Name:** It specifies the name of Cookies.
*   **key:** is not an optional parameter and represents the key value of cookies.
*   **Attribute:** Specifies the information of biscuits. The attribute can be one of the following parameters.
    1.  **Field:** Write only. It specifies cookie sent only to the requested domain name.
    2.  **Expiration:** Specify the expiration date of biscuits. If no data is set, cookies will expire after the session ends.
    3.  **haskeys:** Read-only. It specifies whether the cookie contains a key.
    4.  **Path:** Write only. If specified, Cookie will only be sent to requests of this path. If this property is not set, the application path is used.
    5.  **Safety:** Write only. It means cookies are safe.
*   **Value:** It defines the value assigned to the key or attribute.

**例:**基本上“请求。Cookies”命令用于获取 cookie 值。下面的代码说明了如何返回名为“firstname”的 cookies 的值。

```vb
<%
Response.Cookies("site")="GeeksforGeeks"
sname=Request.Cookies("site")
response.write("Grow with " & sname)
%>
```

**输出:**

```vb
Grow with GeeksforGeeks
```