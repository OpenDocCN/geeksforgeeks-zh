# ASP 服务器。GetLastError()方法(ASP 3.0)

> 原文:[https://www . geesforgeks . org/ASP-server-getlasterror-method-ASP-3-0/](https://www.geeksforgeeks.org/asp-server-getlasterror-method-asp-3-0/)

**ASP 服务器。GetLastError()方法** 用于返回一个 ASP 错误对象，该对象定义了发生的错误情况。一般网站使用默认文件***\ IIS help \ common \ 500-100 . asp***在 ASP 文件中遇到错误。或者我们也可以创建自己的文件。此方法仅在。asp 文件已将任何内容发送到客户端。

**注:**A 500；如果 IIS 在处理 ASP 文件或应用程序的 **Global.asa 文件**时遇到错误，将生成 100 个自定义错误。

**语法:**

```vb
***Server.GetLastError()***
```

***参数值:*** 此方法不包含任何参数值。

***返回值:*** 此方法不返回值。

下面的例子演示了不同类型的错误。基本上有三种类型的错误:

*   ***Pre-processing error:*** In the following example, when IIS tries to include files, there will be an error because the include statement is missing file parameters:

```vb
<!--#include f="header.inc" -->
<%
response.write("sometext")
%>
```

*   ***Script compilation error:*** The following code demonstrates that there will be errors when compiling scripts, because the keyword "next" is missing:

```vb
***<%***
***dim i***
***for i=1 to 10***
 ***........***
***nxt***
***%>***
```

*   ***跑***