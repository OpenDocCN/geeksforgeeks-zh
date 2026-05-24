# ASP 二进制读取方法

> 原文:[https://www.geeksforgeeks.org/asp-binaryread-method/](https://www.geeksforgeeks.org/asp-binaryread-method/)

**ASP BinaryRead 方法**用于检索使用 POST 请求从客户端发送到服务器的数据。此方法将数据存储在安全数组中。安全数组用于存储有关其维数及其界限的信息。

**语法:**

```vb
Request.BinaryRead(count) 

```

**参数值:**这个属性接受一个参数，如上所述，如下所述:

*   **Count** : It contains a counter variable that specifies how many bytes to read from the client before execution.

**示例:**下面的代码使用 **BinaryRead** 方法将请求的内容放入安全数组中。

## HTML

```vb
<%
dim a,b
a=Request.TotalBytes
'fetch the total number of Bytes 
b=Request.BinaryRead(a)
%>
```