# ASP 共享名属性

> 原文:[https://www.geeksforgeeks.org/asp-sharename-property/](https://www.geeksforgeeks.org/asp-sharename-property/)

**ASP 共享名属性**用于返回指定驱动器的网络共享名。

**语法:**

```vb
DriveObject.ShareName 
```

**示例:**下面的代码演示了 ASP 驱动。共享名属性。

## ASP

```vb
<%
dim fs,d
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the required drive
set d=fs.GetDrive("d:")

'Getting the share name of the drive
Response.Write("The share name of drive: " & d.ShareName)

set d=nothing
set fs=nothing
%>
```

**输出**

```vb
The share name of drive: GeeksForGeeks
```