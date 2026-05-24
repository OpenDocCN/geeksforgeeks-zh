# ASP 是现成的属性

> 原文:[https://www.geeksforgeeks.org/asp-isready-property/](https://www.geeksforgeeks.org/asp-isready-property/)

**ASP IsReady 属性**用于返回一个布尔值，该值指定驱动器是否就绪。如果指定的驱动器已准备好，则返回**真**，否则返回**假**。

**语法:**

```vb
DriveObject.IsReady
```

**示例:**下面的代码演示了 ASP 驱动。是已准备好的财产。

## ASP

```vb
<%
dim fs,d,n
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Get the drive to be checked
set d=fs.GetDrive("c:")

n = "Drive " & d.DriveLetter & " is ready: "

'Check if the drive is ready
if d.IsReady=true then
  n=n & "true"
else
  n=n & "false"
end if

'Write out the response
Response.Write(n)

set d=nothing
set fs=nothing
%>
```

**输出:**

```vb
Drive C is ready: true
```