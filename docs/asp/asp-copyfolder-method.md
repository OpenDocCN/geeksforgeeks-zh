# ASP 复制文件夹方法

> 原文:[https://www.geeksforgeeks.org/asp-copyfolder-method/](https://www.geeksforgeeks.org/asp-copyfolder-method/)

**ASP 复制文件夹方法**用于将一个或多个文件夹从源复制到目标。它是文件系统对象的预定义方法。

**语法:**

```vb
FileSystemObject.CopyFolder source,destination[,overwrite] 
```

**参数值:**

*   **Source:** Required attribute. For one or more folders to be copied, it contains a string file that can contain wildcards.
*   **Destination:** is also a required attribute. It specifies the location of a string value copy folder. It does not include wildcards.
*   **Overwrite:** contains a Boolean value indicating whether the existing folder can be overwritten. If true, the file will be overwritten; If it is false, it is not. The default value is true. Please note that if the target has the read-only attribute set, copying the file will fail, regardless of the overwritten value.

**示例:** 下面的示例演示了 CopyFolder 方法。

## Javascript

```vb
<%
'copy all the folders in c:\myfolders\hello
'to the folder c:\pictures

dim fs
set fs=Server.CreateObject("Scripting.FileSystemObject")
fs.CopyFolder "c:\myfolders\hello\*","c:\pictures\"
response.write("Folder Copied")
set fs=nothing
%>
```

**输出:**

```vb
Folder Copied
```