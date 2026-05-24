# ASP 获取文件夹方法

> 原文:[https://www.geeksforgeeks.org/asp-getfolder-method/](https://www.geeksforgeeks.org/asp-getfolder-method/)

**ASP 获取文件夹方法**用于返回指定路径的文件夹对应的文件夹对象。它是文件系统对象的内置方法。

**语法:**

```vb
FileSystemObject.GetFolder(path)
```

**参数值:**

*   **Path:** Required attribute. It specifies the path of the specified folder.

**示例 1:** 下面的示例说明了 ASP GetFolder 方法。

## ASP

```vb
<%
dim fs,f
set fs=Server.CreateObject("Scripting.FileSystemObject")
set f=fs.GetFolder("d:\hello\")
Response.Write("The folder was last modified on: ")
Response.Write(f.DateLastModified)
set f=nothing
set fs=nothing
%>
```