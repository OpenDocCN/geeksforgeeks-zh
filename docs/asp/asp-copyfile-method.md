# ASP 复制文件法

> 原文:[https://www.geeksforgeeks.org/asp-copyfile-method/](https://www.geeksforgeeks.org/asp-copyfile-method/)

**ASP 复制文件方法**用于将一个或多个文件从一个地方复制到另一个地方。它是文件系统对象的预定义方法。

**语法:**

```vb
FileSystemObject.CopyFile source,destination[,overwrite] 
```

**参数值:**

*   **Source:** *Required attribute.* It contains a string file, which can contain wildcards for one or more files to be copied.
*   **Destination:** is also a required attribute. It specifies the location where a string value is copied to the file. It does not include wildcards.
*   **Overwrite:** contains a Boolean value indicating whether the existing file can be overwritten. If true, the file will be overwritten; If it is false, it is not. The default value is true. Please note that if the target has the read-only attribute set, copying the file will fail, regardless of the overwritten value.

**示例代码:**下面的示例演示了复制文件方法。

## ASP

```vb
<%
dim gfg
set gfg=Server.CreateObject("Scripting.FileSystemObject")
gfg.CopyFile "c:\Folder1\A\*.txt","c:\Folder2\"
response.write("File is Copied")
set gfg=nothing
%>
```

**输出:**

```vb
File is Copied 
```