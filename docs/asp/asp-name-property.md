# ASP 名称属性

> 原文:[https://www.geeksforgeeks.org/asp-name-property/](https://www.geeksforgeeks.org/asp-name-property/)

**ASP 名称属性**用于返回和设置指定文件或文件夹的名称。

**语法:**

*   **for file object:**

```vb
FileObject.Name[=newname]
```

*   **for folder objects:**

```vb
FolderObject.Name[=newname]
```

**参数值:**

*   **newname:** is an optional attribute. It specifies the new name of the file or folder.

**示例-1:** 下面的代码返回文件的名称。

## ASP

```vb
<%
dim fs,f
set fs=Server.CreateObject("Scripting.FileSystemObject")
set f=fs.GetFile("d:\GFG.txt")
Response.Write("The name of the file is: ")
Response.Write(f.Name)
set f=nothing
set fs=nothing
%>
```