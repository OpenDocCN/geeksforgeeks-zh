# ASP 总大小属性

> 原文:[https://www.geeksforgeeks.org/asp-totalsize-property/](https://www.geeksforgeeks.org/asp-totalsize-property/)

**ASP TotalSize 属性**用于返回系统上指定驱动器的总大小。它以字节为单位返回值。

**语法:**

```vb
DriveObject.TotalSize
```

**示例:**下面的代码演示了 ASP 驱动。总大小属性。

## ASP

```vb
<%
dim fs,d
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the drive
set d=fs.GetDrive("d:")

'Getting the total size of the drive
Response.Write("Total size of drive: " & d.TotalSize & " bytes")

set d=nothing
set fs=nothing
%>
```

**输出:**

```vb
Total size of drive: 499368587264 bytes
```