# ASP 删除文件夹方法

> 原文:[https://www.geeksforgeeks.org/asp-deletefolder-method/](https://www.geeksforgeeks.org/asp-deletefolder-method/)

**ASP 删除文件夹方法**用于从服务器中删除一个或多个文件夹。如果我们想删除一个不存在的文件夹，它会返回一个错误。

**语法:**

```vb
FileSystemObject.DeleteFolder(foldername[,force])
```

**参数值:**

*   **Folder Name:** Specify the name of the folder to be deleted.
*   **Force:** It is an optional attribute. It contains a Boolean value indicating whether the read-only folder will be deleted. Setting it to true means that the read-only folder will be deleted. True indicates that the False will not be deleted.

**示例:**下面的示例演示了**删除文件夹方法。**

## ASP

```vb
<%
dim gfg
set gfg=Server.CreateObject("Scripting.FileSystemObject")
if gfg.FolderExists("C:\Folder2\B") then
 gfg.DeleteFolder("C:\Folder2\B")
 response.write("Folder is Deleted")
end if
set gfg=nothing
%>
```

**输出:**

```vb
Folder is Deleted
```