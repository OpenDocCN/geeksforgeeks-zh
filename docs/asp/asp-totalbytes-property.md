# ASP 总字节属性

> 原文:[https://www.geeksforgeeks.org/asp-totalbytes-property/](https://www.geeksforgeeks.org/asp-totalbytes-property/)

**ASP TotalBytes** 是只读属性。此属性用于返回客户端将通过请求正文发送的总字节数。

**语法:**

```vb
Counter = Request.TotalBytes

```

**参数值:**该属性接受一个参数，如上所述，如下所述:

*   **[counter:** It contains a counter variable, which is used to receive the total number of bytes sent by the client in the request body.

**示例**:下面的代码使用了一个计数器变量来存储包含的总字节数。

## HTML

```vb
<%
dim countByte
'counter variable that counts the total number of bytes
countByte=Request.TotalBytes
%>
```