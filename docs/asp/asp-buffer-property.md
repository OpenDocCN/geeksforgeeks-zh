# ASP 缓冲属性

> 原文:[https://www.geeksforgeeks.org/asp-buffer-property/](https://www.geeksforgeeks.org/asp-buffer-property/)

ASP 中的**缓冲属性**用于指定输出是否缓冲。当页面缓冲时，服务器不响应或发送数据到客户端，直到剩余的服务器脚本被成功处理，或直到调用**刷新**或**结束**方法。

*   **刷新方法:**此用于立即发送缓冲的 HTML 输出。
*   **结束方式:**此为停止脚本的工作进程。它通常返回当前结果。**T3】**

当服务器开始向服务器发送数据后，此属性不能中断。**缓冲区**属性应该设置为**的第一行代码。asp** 文件。

**语法:**

```vb
response.Buffer[=flag]
```

**参数值:**该属性接受如上所述的单个值，如下所述:

*   **标志:** 它包含指定输出是否应该缓冲的布尔值。

1.  **true:** 定义页面被缓冲。
2.  **假:**指定输出不会被缓冲。

**注意:**如果设置了**响应。缓冲=真**在无限循环中，输出永远不会发送到客户端。

**示例 1:** 在本例中，Buffer 属性设置为 true，因此没有将发送到浏览器的输出。

## 超文本标记语言

```vb
<!-- Buffer Property is set to true -->
<% response.Buffer=true %>
<html>
    <body>

<p>
            GeeksforGeeks is computer 
            science portal for Geeks.
        </p>

    </body>
</html>
```

**输出:**这里标志值设置为真，所以整个服务器脚本已经成功编译，然后输出才会发送到客户端。

```vb
GeeksforGeeks is computer science portal for Geeks.
```

**示例 2:** 以下示例说明缓冲区属性设置为假，因此输出将被发送到浏览器。

## 超文本标记语言

```vb
<!-- Buffer Property is set to true -->
<% response.Buffer=false %>
<html>
    <body>

<p>
            GeeksforGeeks is computer 
            science portal for Geeks.
        </p>

    </body>
</html>
```

**输出:**这里的标志值设置为 false，这样输出就不会等待编译整个服务器脚本，它只会将输出发送到客户端。

```vb
GeeksforGeeks is computer science portal for Geeks.
```