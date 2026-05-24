# ASP 响应。饼干收集

> 原文:[https://www . geesforgeks . org/ASP-response-cookies-collection/](https://www.geeksforgeeks.org/asp-response-cookies-collection/)

基本上，Cookies 是存储在用户计算机上的小文件。它用于保存特定客户端和网站的少量数据，可以由网络服务器或客户端计算机访问。

**回应。饼干收集**用于设置饼干的收集值。如果指定的 cookie 不存在，则会创建它。如果 cookie 存在，它将接受新值，旧值将被丢弃。

**语法:**

```vb
Response.Cookies(name)[(key)|.attribute]=value
```

**参数:**

*   **Name:** Specify the name of the biscuit.
*   **key:** is not an optional parameter and represents the key value of cookies.
*   **Attribute:** Specifies the information of biscuits. The attribute can be one of the following parameters.
    1.  **Field:** Write only. It specifies cookie sent only to the requested domain name.
    2.  **Expiration** : Specify the expiration date of biscuits. If no data is set, cookies will expire after the session ends.
    3.  **haskeys:** Read-only. It specifies whether the cookie contains a key.
    4.  **Path:** Write only. If specified, Cookie will only be sent to requests of this path. If this property is not set, the application path is used.
    5.  **Safety:** Write only. It means cookies are safe.

*   **Value:** It defines the value assigned to the key or attribute.

**示例 1:** 下面的代码说明了如何创建名为“网站”的 cookies，并为其分配值“极客博客”。

```vb
<%
Response.Cookies("website")="GeeksForGeeks"
%>
```

**示例 2:** 下面的示例演示了如何为 cookie 设置值并为其属性赋值。

```vb
<%  
 Response.Cookies("Type") = "fruits"  
 Response.Cookies("Type").Expires = "July 31, 2001"  
 Response.Cookies("Type").Path = "/"  
%>
```