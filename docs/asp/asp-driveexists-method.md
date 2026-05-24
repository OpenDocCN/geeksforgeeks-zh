# ASP 驱动存在方法

> 原文:[https://www.geeksforgeeks.org/asp-driveexists-method/](https://www.geeksforgeeks.org/asp-driveexists-method/)

**ASP 驱动程序存在方法**用于返回布尔值，该值指示特定驱动程序是否将退出。返回 true 表示特定驱动器退出，如果特定驱动器不退出，则返回 false。

**语法**

```vb
FileSystemObject.DriveExists(drive) 
```

**参数值**

*   **Driver:** is a required attribute. It specifies the drive letter or the full path description.

**示例:** 下面的示例演示了 DriveExists 方法。

## ASP

```vb
<%
dim gfg
set gfg=Server.CreateObject("Scripting.FileSystemObject")
if gfg.DriveExists("d:")=true then
 response.write("Drive d: exists!")
else
 response.write("Drive d: does not exist.")
end If
set gfg=nothing
%>
```

**输出:**

```vb
Drive d: exists
```