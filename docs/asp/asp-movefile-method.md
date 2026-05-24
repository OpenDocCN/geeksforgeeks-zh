# ASP 移动文件方法

> 原文:[https://www.geeksforgeeks.org/asp-movefile-method/](https://www.geeksforgeeks.org/asp-movefile-method/)

***ASP 移动文件方法*** 用于将一个或多个文件从一个地方移动到另一个地方。它是文件系统对象的内置方法。

**语法**

```vb
FileSystemObject.MoveFile source,destination
```

**参数值:**

**来源:**必选属性。对于要移动的一个或多个文件，它包含一个可以包含通配符的字符串文件。

***目的地:*** 也是必选属性。它指定一个字符串值将文件移动到哪里。它不包括通配符。

**示例:** *下面的代码说明了 ASP MoveFile 方法。*

## ASP

```vb
<%
dim fs
set fs=Server.CreateObject("Scripting.FileSystemObject")
fs.MoveFile "C:\Folder1\A\A.txt","C:\Folder2\B\"
response.write("The location of the file is changed")
set fs=nothing
%>
```

**输出:**

```vb
The location of the file is changed
```