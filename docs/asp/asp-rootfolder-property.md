# ASP 根文件夹属性

> 原文:[https://www.geeksforgeeks.org/asp-rootfolder-property/](https://www.geeksforgeeks.org/asp-rootfolder-property/)

**ASP 根文件夹属性**用于返回一个文件夹对象，该对象指示指定驱动器的根文件夹。

**语法:**

```vb
DriveObject.RootFolder 
```

**示例:**下面的代码说明了 ASP 驱动。根文件夹属性。

## ASP

```vb
<%
dim fs,d
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the drive
set d=fs.GetDrive("d:")

'Getting the root folder of the drive
Response.Write("Root folder of the drive is: " & d.RootFolder)

set d=nothing
set fs=nothing
%>
```

**输出:**

```vb
Root folder of the drive is: D:\
```