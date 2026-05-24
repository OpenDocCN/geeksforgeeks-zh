# ASP 过期属性

> 原文:[https://www.geeksforgeeks.org/asp-expires-property/](https://www.geeksforgeeks.org/asp-expires-property/)

**ASP 过期属性**用于设置页面在被 v 浏览器抓取之前过期的持续时间。它是用户在过期前返回的同一个页面，显示缓存的版本。

**语法:**

```vb
response.Expires[=number] 

```

**参数值:**它包含一个数值，表示页面过期前的持续时间，以分钟为单位。

**示例 1:** 下面的代码说明了如何使用 Expires 属性的负数来立即终止响应。

## HTML

```vb
<% Response.Expires = -1 %> 
```