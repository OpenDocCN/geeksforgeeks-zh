# ASP 内容类型属性

> 原文:[https://www.geeksforgeeks.org/asp-contenttype-property/](https://www.geeksforgeeks.org/asp-contenttype-property/)

**ASP 内容类型属性**用于设置响应头对象的 HTTP 内容类型/子类型。默认值为文本/HTML

**语法:**

```vb
response.ContentType[=contenttype] 

```

**参数值:**包含代表内容类型的字符串值，即**内容类型**。

**示例 1:** 该示例说明了 asp 页面具有的各种类型的内容。

## HTML

```vb
<%response.ContentType="text/HTML"%>
<%response.ContentType="image/GIF"%>
<%response.ContentType="image/JPEG"%>
<%response.ContentType="text/plain"%>
```