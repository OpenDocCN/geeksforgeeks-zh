# ASP 字符集属性

> 原文:[https://www.geeksforgeeks.org/asp-charset-property/](https://www.geeksforgeeks.org/asp-charset-property/)

**ASP 字符集属性**用于将字符集的名称附加到响应对象中的内容类型头。

例如- ISO-8859-13。默认字符集是 ISO-LATIN-1。

**语法** :

```vb
response.Charset(charsetname)
```

**参数值:**它包含值，即**字符集名称**，指定 asp 页面的字符集名称。

**示例:**

*   If the character set attribute is not set in the asp page, the content type title will look like:

```vb
content-type:text/html
```

*   If the ASP page contains the same attributes

```vb
<% response.Charset=ISO-8859-13 >
```

*   The title of the content type will be as follows:

```vb
content-type:text/html; Charset=ISO-8859-13
```