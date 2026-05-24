# ASP 自由空间属性

> 原文:[https://www.geeksforgeeks.org/asp-freespace-property/](https://www.geeksforgeeks.org/asp-freespace-property/)

**ASP 空闲空间属性**用于返回在特定驱动器上提供给用户的空闲存储空间量。它以字节为单位返回一个值。

**语法:**

```vb
DriveObject.FreeSpace
```

**示例:**下面的代码说明了 ASP 驱动。自由空间财产。

## ASP

```vb
<%
dim fs,dr
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the drive to be checked
set dr=fs.GetDrive("d:")
Response.Write("The drive " & dr)

'Getting the free space on the drive
Response.Write(" has " & dr.FreeSpace & " free space")

set dr=nothing
set fs=nothing
%>
```

**输出:**

```vb
The drive D: has 8237483934 free space
```