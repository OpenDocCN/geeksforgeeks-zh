# ASP 可用空间属性

> 原文:[https://www.geeksforgeeks.org/asp-availablespace-property/](https://www.geeksforgeeks.org/asp-availablespace-property/)

**ASP 可用空间属性**用于返回驱动器上剩余的可用空间量。它以字节为单位返回值。

**语法:**

```vb
DriveObject.AvailableSpace
```

**示例:**下面的代码说明了 ASP 驱动。可用空间属性。

## ASP

```vb
<%
Dim fs,dr
Set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the drive to be checked
Set dr=fs.GetDrive("d:")

Response.Write("The drive: " & dr)

'Getting the avaialable space of the drive
Response.Write(" has available space: " & dr.AvailableSpace)

set dr=nothing
set fs=nothing
%>
```

**输出:**

```vb
The drive: D: has available space: 992345694
```