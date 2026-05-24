# ASP 清除方法

> 原文:[https://www.geeksforgeeks.org/asp-clear-method/](https://www.geeksforgeeks.org/asp-clear-method/)

**ASP 清除方法**用于清除或擦除缓冲的 HTML 输出。此方法仅擦除响应正文，不影响响应标题。当**响应缓冲区**设置为 ***假，*** 调用后会显示错误消息。

**语法:**

```vb
response.Clear
```

**参数值:**不包含任何参数。

**返回值**:这个方法没有返回值。

**例:**

```vb
<%
// Buffer set to true
response.Buffer=true
%>
<%
 // call clear Method
response.Clear
%>
```

**输出:**

```vb
None
```

**参考文献:**

*   https://docs。微软。com/en-us/以前版本/IIS/6.0-SDK/ms525713(v = vs . 90)