# ASP 结束方式

> 原文:[https://www.geeksforgeeks.org/asp-end-method/](https://www.geeksforgeeks.org/asp-end-method/)

**ASP 结束方法**用于确保 web 服务器停止处理脚本，并返回当前结果。剩余的结果将不会被处理。

**语法:**

```vb
Response.End 

```

**参数值:**此方法不接受任何参数。

**示例:**这里我们将停止网络服务器，在特定位置后继续前进。

## HTML

```vb
<html>
  <body>

<p> 
      GeeksforGeeks 
    </p>

    <!-- Calling the end method -->
    <% Response.End %>

<p>
    <!-- This paragraph is not sent 
         to the Browser -->
       Hello Geeks 
    </p>

  </body>
</html>
```

**输出:**

```vb
GeeksforGeeks

```