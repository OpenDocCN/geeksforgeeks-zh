# ASP 请求。表单集合

> 原文:[https://www.geeksforgeeks.org/asp-request-form-collection/](https://www.geeksforgeeks.org/asp-request-form-collection/)

**请求。ASP 中的表单集合**用于返回发布到 HTTP 请求体的表单元素集合，表单使用 POST 方法。

**语法**

```vb
Request.Form( element )[(index)|.Count]
```

**参数:**

*   **Element:** Specify the name of the form element. This is a required attribute.
*   **Index** : an optional parameter that indicates the position of the form element used for access. Can be any integer from 1 to n.

**示例 1:** 下面的代码使用 for 循环访问用户填写的表单值。我们可以这样检索这些值:

## 【PHP】

```vb
<% 
for i=1 to Request.Form("color").Count
 Response.Write(Request.Form("color")(i) & "<br>")
next
%>
```