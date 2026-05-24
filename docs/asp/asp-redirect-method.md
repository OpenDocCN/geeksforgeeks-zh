# ASP 重定向方法

> 原文:[https://www.geeksforgeeks.org/asp-redirect-method/](https://www.geeksforgeeks.org/asp-redirect-method/)

**ASP 重定向方法**用于将客户端重定向到不同的网址。它是响应对象的预定义方法。

**语法:**

```vb
Response.Redirect URL

```

**参数值:**该方法接受如上所述的单个参数，如下所述:

*   **Website:** It defines a uniform resource locator, which represents the location where the browser is redirected.

**返回值**:此方法不返回值。

**示例**:下面的代码将用户重定向到极客网站。

```vb
<%
Response.Redirect "https://www.GeelsforGeeks.org.in"
%>

```