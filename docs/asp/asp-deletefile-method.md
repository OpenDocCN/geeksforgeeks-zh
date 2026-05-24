# ASP 删除文件方法

> 原文:[https://www.geeksforgeeks.org/asp-deletefile-method/](https://www.geeksforgeeks.org/asp-deletefile-method/)

**ASP 删除文件方法**用于从服务器中删除一个或多个文件。如果我们想删除一个不存在的文件，它会返回一个错误。

**语法:**

```vb
FileSystemObject.DeleteFile(filename[,force])
```

**参数值:**

*   **File name:** Specify the name of the file to be deleted.
*   **Force:** is an optional attribute. It contains a Boolean value indicating whether the read-only file will be deleted. Setting it to true means that the read-only file will be deleted. True indicates that the False will not be deleted.

**示例**:下面的示例演示了**删除文件**的方法。

## ASP

```vb
<%
dim fs
Set fs=Server.CreateObject("Scripting.FileSystemObject")
if fs.FileExists("c:\pictures\a.txt") then
response.write("Exist file ")
 fs.DeleteFile("c:\pictures\a.txt")
 response.write("is Deleted")
end if
set fs=nothing
%>
```

**输出:**

```vb
Exist file is Deleted
```