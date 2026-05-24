# ASP 卷名属性

> 原文:[https://www.geeksforgeeks.org/asp-volumename-property/](https://www.geeksforgeeks.org/asp-volumename-property/)

**ASP 卷名属性**用于设置或返回指定驱动器的卷名。

**语法:**

```vb
DriveObject.VolumeName[=newname]
```

**参数:**该属性有一个参数，如上所述，如下所述:

*   **New Name:** It specifies a new name that must be set for the drive. This is an optional parameter.

**示例:**下面的代码演示了 ASP 驱动。卷名属性。

## ASP

```vb
<%
dim fs,d1,d2
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the drive
set d1=fs.GetDrive("D:")

'Getting the name of the drive
Response.Write("The volume name is: " & d1.VolumeName)

'Getting the drive
set d2=fs.GetDrive("F:")

'Getting the name of the drive
Response.Write("<br>The volume name is: " & d2.VolumeName)

set d1=nothing
set d2=nothing
set fs=nothing
%>
```

**输出:**

```vb
The volume name is: Windows
The volume name is: Software
```