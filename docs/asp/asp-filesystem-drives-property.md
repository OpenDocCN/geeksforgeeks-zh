# ASP 文件系统。驱动属性

> 原文:[https://www . geesforgeks . org/ASP-file system-drives-property/](https://www.geeksforgeeks.org/asp-filesystem-drives-property/)

**文件系统。驱动器** **属性**用于返回系统中所有驱动器对象的只读集合。单个的驱动元件可以被砍掉以获得它们的属性。

**语法:**

```vb
FileSystemObject.Drives
```

**示例:**下面的代码说明了如何显示系统上的所有驱动器号。

## ASP

```vb
<%
dim fs,fo,x
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Get all the drives on the system
set fo=fs.Drives

Response.write("The drives present are:")
for each x in fo
  'Print the name of all drives on system
  Response.write("<br> Drive: " & x.DriveLetter)
next

set fo=nothing
set fs=nothing
%>
```

**输出:**

```vb
The drives present are:
Drive: C
Drive: D
Drive: E
Drive: F

```