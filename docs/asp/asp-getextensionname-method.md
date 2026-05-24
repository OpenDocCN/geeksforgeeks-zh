# ASP GetExtensionName 方法

> 原文:[https://www.geeksforgeeks.org/asp-getextensionname-method/](https://www.geeksforgeeks.org/asp-getextensionname-method/)

ASP 中的 **GetExtensionName 方法**用于返回一个字符串值，该字符串值代表指定路径中最后一个组件的文件扩展名。这是一个预定义的**文件系统** *对象的方法。*

**语法:**

```vb
FileSystemObject.GetExtensionName(path)
```

**参数值:**

*   ***Path:*** is a required attribute. It specifies the path of the component whose extension you want to return.

**示例 1:** 下面的示例代码演示了 **GetExtensionName 方法。**

## ASP

```vb
<%
dim fs
set fs=Server.CreateObject("Scripting.FileSystemObject")
Response.Write(fs.GetExtensionName("d:\sudo\GFG.asp"))
set fs=nothing
%>
```

**输出:**

```vb
asp
```

**例 2:**

## ASP

```vb
<%
dim fs
set fs=Server.CreateObject("Scripting.FileSystemObject")
Response.Write(fs.GetExtensionName("d:\sudo\GFG.htm"))
set fs=nothing
%>
```

**输出:**

```vb
htm
```