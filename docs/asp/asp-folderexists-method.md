# ASP 文件夹存在方法

> 原文:[https://www.geeksforgeeks.org/asp-folderexists-method/](https://www.geeksforgeeks.org/asp-folderexists-method/)

ASP 中的 ***文件夹存在方法*** 用于返回指示特定文件夹是否存在的布尔值。它返回 true 表示特定文件夹存在，如果特定文件夹不存在，则返回 false。

**语法:**

```vb
***FileSystemObject.FolderExists(foldername)***
```

**参数值:**

*   **Folder Name:** Specifies the name of the folder whose existence will be checked.

**示例:** 下面的代码演示了 **FolderExists 方法。**

## ASP

```vb
<%
dim fs
set fs=Server.CreateObject("Scripting.FileSystemObject")
if fs.FolderExists("d:\GFG")=true then
 response.write("Folder d:\GFG exists!")
else
 response.write("Folder d:\GFG does not exist!")
end if
set fs=nothing
%>
```

**输出:**

```vb
Folder d:\GFG exists
```