# ASP 追加法

> 原文:[https://www.geeksforgeeks.org/asp-appendtolog-method/](https://www.geeksforgeeks.org/asp-appendtolog-method/)

**ASP 追加方法**用于在该请求的服务器日志条目的末尾添加一个字符串。这个方法可以调用很多次。它用于在该请求的网络服务器日志条目的末尾追加一个字符串。

**语法:**

```vb
response.AppendToLog string
```

**参数值:**

*   **String:** It contains a string value representing the text attached to the log file. It does not contain comma characters.

**返回值:**此方法不返回值。

**示例:**下面的代码将文本“内容更新”添加到日志文件中:

```vb
<%
  Response.AppendToLog "My log message"
%>
```