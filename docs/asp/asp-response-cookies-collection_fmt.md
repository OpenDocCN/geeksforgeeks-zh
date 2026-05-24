# ASP Response.Cookies 集合

> 原文：[https://www.geeksforgeeks.org/asp-response-cookies-collection/](https://www.geeksforgeeks.org/asp-response-cookies-collection/)

基本上，Cookies 是存储在用户计算机上的小文件。它用于保存特定客户端和网站的少量数据，可以由网络服务器或客户端计算机访问。

`Response.Cookies` 集合用于设置 Cookie 的集合值。如果指定的 Cookie 不存在，则会创建它。如果 Cookie 存在，它将接受新值，旧值将被丢弃。

## 语法

```vb
Response.Cookies(name)[(key)|.attribute]=value
```

## 参数

*   `Name`：指定 Cookie 的名称。
*   `key`：这不是一个可选参数，代表 Cookie 的键值。
*   `Attribute`：指定 Cookie 的信息。该属性可以是以下参数之一。
    1.  `Domain`：只写。指定仅将 Cookie 发送到请求的域名。
    2.  `Expires`：指定 Cookie 的过期日期。如果未设置数据，Cookie 将在会话结束后过期。
    3.  `HasKeys`：只读。指定 Cookie 是否包含键。
    4.  `Path`：只写。如果指定，Cookie 将仅发送到此路径的请求。如果未设置此属性，则使用应用程序路径。
    5.  `Secure`：只写。表示 Cookie 是安全的。

*   `Value`：定义分配给键或属性的值。

## 示例 1

下面的代码说明了如何创建名为 "website" 的 Cookie，并为其分配值 "GeeksForGeeks"。

```vb
<%
Response.Cookies("website")="GeeksForGeeks"
%>
```

## 示例 2

下面的示例演示了如何为 Cookie 设置值并为其属性赋值。

```vb
<%
Response.Cookies("Type") = "fruits"
Response.Cookies("Type").Expires = "July 31, 2001"
Response.Cookies("Type").Path = "/"
%>
```