# ASP GetDrive 方法

> 原文:[https://www.geeksforgeeks.org/asp-getdrive-method/](https://www.geeksforgeeks.org/asp-getdrive-method/)

ASP 中的`GetDrive`方法用于返回对应于指定路径中驱动器的驱动对象。这是一个预定义的`FileSystemObject`对象的方法。

**语法:**

```vb
FileSystemObject.GetDrive(drivespec) 
```

**参数值:**

*   `drivespec`: 必需的属性。它可以是驱动器盘符（c）、带冒号的驱动器盘符（c:）、带冒号和路径分隔符的驱动器盘符（c:\），或任何网络共享规范（\\computer2\share1）。

**示例代码:**下面的代码演示了 ASP GetDrive 方法。

## ASP

```vb
<%
dim fs,d
set fs=Server.CreateObject("Scripting.FileSystemObject")
set d=fs.GetDrive("d:\")
response.write("Drive is:" + d)
set fs=nothing
%>
```

**输出:**

```vb
Drive is: d
```