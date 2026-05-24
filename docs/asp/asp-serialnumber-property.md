# ASP 序列号属性

> 原文:[https://www.geeksforgeeks.org/asp-serialnumber-property/](https://www.geeksforgeeks.org/asp-serialnumber-property/)

**ASP 序列号属性**用于返回特定驱动器的序列号。

**语法:**

```vb
DriveObject.SerialNumber
```

**示例:**下面的代码演示了 ASP 驱动。序列号属性。

## ASP

```vb
<%
dim fs,dr
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the required drive
set dr=fs.GetDrive("d:")

'Getting the serial number of the drive
Response.Write("Serial No. of the drive is " & dr.SerialNumber)

set dr=nothing
set fs=nothing
%>
```

**输出:**

```vb
Serial No. of the drive is 1108724040
```