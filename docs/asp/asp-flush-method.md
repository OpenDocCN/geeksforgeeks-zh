# ASP 冲洗法

> 原文:[https://www.geeksforgeeks.org/asp-flush-method/](https://www.geeksforgeeks.org/asp-flush-method/)

**ASP 刷新方法**用于立即发送缓冲输出。如果**响应，该方法返回运行时错误。缓冲**设置为假。

**语法** :

```vb
Response.Flush 

```

**示例:**下面的示例说明了冲水方法**。****回应。刷新**不会等到完成整个脚本才返回输出给客户端。

## HTML

```vb
<!-- Flush method set to true -->
< % Response.Buffer=true% >
<html>  
   <body>

<p>GeeksforGeeks</p>

<p>Hello Geeks</p>

     <% Response.Flush%>
   </body>
</html>
```

**输出:**

```vb
GeeksForGeeks
Hello Geeks 

```