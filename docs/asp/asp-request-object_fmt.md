# ASP 请求对象

> 原文：[https://www.geeksforgeeks.org/asp-request-object/](https://www.geeksforgeeks.org/asp-request-object/)

**ASP 请求对象**用于从客户端浏览器中检索信息。当客户端想要从服务器请求特定页面时，使用请求对象。

请求对象具有下面给出的属性、方法和集合。

## 集合

*   `Client certificate`：用于包含要存储在客户端证书中的所有字段值。
*   `Cookies`：用于返回要作为 HTTP 请求发送的一组 Cookie 的所有值。
*   `Form`：用于返回发布到 HTTP 请求正文的表单元素集合。
*   `Query string`：用于获取将出现在 HTTP 查询字符串中的变量值。
*   `Server variable`：用于返回所有服务器变量的值。

## 属性

*   `Total Bytes`：用于获取通过请求正文发送到服务器的总字节数。

## 方法

*   `Binary read()`：此方法用于通过 POST 请求检索从客户端发送到服务器的数据。此方法将数据存储在安全数组中。安全数组用于存储有关其维度和边界的信息。

## 示例

下面的代码说明了如何返回名为“site”的 Cookie 的值。（`Request.Cookies` 用于获取 Cookie 值）

```vb
<%
Response.Cookies("site")="GeeksforGeeks"
sitename=Request.Cookies("site")
response.write("Lets Code with " & sitename)
%>
```

## 输出

```vb
Lets code with GeeksforGeeks
```