# ASP 请求。表单集合

> 原文：`https://www.geeksforgeeks.org/asp-request-form-collection/`

`Request.Form` 集合用于返回通过 POST 方法发布到 HTTP 请求体的表单元素集合。

## 语法

```vb
Request.Form( element )[(index)|.Count]
```

## 参数

*   `element`：指定表单元素的名称。此为必需属性。
*   `index`：一个可选参数，指示用于访问的表单元素的位置。可以是 1 到 n 之间的任意整数。

## 示例 1

下面的代码使用 `for` 循环访问用户填写的表单值。我们可以这样检索这些值：

### 【PHP】

```vb
<% 
for i=1 to Request.Form("color").Count
    Response.Write(Request.Form("color")(i) & "<br>")
next
%>
```