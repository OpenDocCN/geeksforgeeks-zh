# ASP 删除方法

> 原文:[https://www.geeksforgeeks.org/asp-delete-method/](https://www.geeksforgeeks.org/asp-delete-method/)

**ASP 文件。删除方法**用于从系统中删除特定的文件或文件夹。

**语法**

*   [**is the file object:**](https://www.geeksforgeeks.org/asp-deletefile-method/)

```vb
FileObject.Delete[(force)]
```

*   [**is the folder object:**](https://www.geeksforgeeks.org/asp-deletefolder-method/)

```vb
FileObject.Delete[(force)]
```

**参数值:**

*   **Force:** is an optional attribute. It contains a Boolean value indicating whether the read-only file will be deleted. Setting it to true means that the read-only file will be deleted. True indicates that the False will not be deleted.

**示例 1:** 下面的代码说明了 **ASP 文件。删除方法**。

## ASP

```vb
<%
dim fs,f
set fs=Server.CreateObject("Scripting.FileSystemObject")
set f=fs.GetFile("d:\GFG.txt")
f.Delete
response.write("GFG.txt file is deleted")
set f=nothing
set fs=nothing
%>
```