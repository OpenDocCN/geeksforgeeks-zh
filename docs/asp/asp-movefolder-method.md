# ASP 移动文件夹方法

> 原文:[https://www.geeksforgeeks.org/asp-movefolder-method/](https://www.geeksforgeeks.org/asp-movefolder-method/)

***ASP 移动文件夹方法*** 用于将一个或多个文件夹从一个地方移动到另一个地方。它是文件系统对象的内置方法。

**语法:**

```vb
FileSystemObject.MoveFolder source,destination
```

***参数值:***

**来源:**必选属性。对于要移动的一个或多个文件夹，它包含一个可以包含通配符的字符串文件。

***目的地:*** 也是必选属性。它指定字符串值“将文件夹文件或文件夹移动到哪里”。它不包括通配符。

**示例代码:** 下面的代码说明了 ASP MoveFolder 方法。

## 动态服务器页面

```vb
<%
dim fs
set fs=Server.CreateObject("Scripting.FileSystemObject")
fs.MoveFolder "C:\Folder1\A","C:\Folder2\B\"
set fs=nothing
%>
```

**输出:**

**之前:**T0】

**之后:**T0】