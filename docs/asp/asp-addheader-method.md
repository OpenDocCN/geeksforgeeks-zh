# ASP 添加标题方法

> 原文:[https://www.geeksforgeeks.org/asp-addheader-method/](https://www.geeksforgeeks.org/asp-addheader-method/)

**ASP 添加头方法**用于指定为 HTTP 头添加一个新的名称，并为 HTTP 响应提供一个给定值。这是一个**回应**类型对象的方法。

*   Once a title is added, it cannot be deleted.
*   Before sending any output to the client, you must call this method unless you respond. The buffer is set to true.

**语法:**

```vb
response.AddHeader name,value

```

**参数值:**该方法接受两个参数，如上所述，如下所述:

*   **Name** : defines the name of the new header variable. The name cannot contain any underscores (_).
*   **Value** : defines the initial value of the new header variable.

**返回值:**这个方法没有返回值。

**例 1:**

```vb
<% Response.AddHeader "WARNING","Error message text %>

```

**示例 2:** 下面的代码使用 AddHeader 方法请求客户端使用基本身份验证。

```vb
<% Response.Addheader "WWW-Authenticate", "BASIC" %>

```

**例 3:**

```vb
<% Response.AddHeader "CustomHeader", "CustomValue" %>
```

**参考:**[https://docs . Microsoft . com/en-us/previous-versions/IIS/6.0-SDK/ms524327(v = vs . 90)](https://docs.microsoft.com/en-us/previous-versions/iis/6.0-sdk/ms524327(v=vs.90))