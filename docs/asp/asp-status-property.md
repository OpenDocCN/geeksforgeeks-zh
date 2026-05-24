# ASP 状态属性

> 原文:[https://www.geeksforgeeks.org/asp-status-property/](https://www.geeksforgeeks.org/asp-status-property/)

**ASP 状态属性**用于指定用户返回的 ASP 页面的状态值。此属性还用于更改 asp 页面的状态。

**语法:**

```vb
response.Status=statusdescription  

```

**参数值:**该属性接受如上所述的单个值，描述如下:

*   **statusdescriptio** n: indicates three digits and specifies the description of the code.

**注意:**错误 404 表示找不到页面。

**示例:**下面的代码说明了 ASP 状态属性。

## HTML

```vb
<%
ip=request.ServerVariables("REMOTE_ADDR")
if ip<>"194.248.333.500" then
 response.Status="401 Unauthorized"
 response.Write(response.Status)
 response.End
end if
%>
```