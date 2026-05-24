# ASP 服务器。URLEncode 方法

> 原文:[https://www.geeksforgeeks.org/asp-server-urlencode-method/](https://www.geeksforgeeks.org/asp-server-urlencode-method/)

**ASP 服务器。URLEncode 方法**用于应用 URL 编码规则转换为指定的字符串。下面给出的 URLEncode 将字符转换如下:

*   The space () is converted to a plus sign (+).
*   Non-alphanumeric characters are escaped to hexadecimal representation.

***语法:***

```vb
***Server.URLEncode(str***ing)
```

***参数值:*** 它包含一个 ***字符串*** 值，指定要编码的字符串。

***例:***

## ASP

```vb
<%
response.write(Server.URLEncode("https://www.geeksforgeeks.org"))
%>
```

***输出:***

```vb
https%3A%2F%2Fwww%2Egeeksforgeeks%2Eorg
```