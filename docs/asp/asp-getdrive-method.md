# ASP GetDrive 方法

> 原文:[https://www.geeksforgeeks.org/asp-getdrive-method/](https://www.geeksforgeeks.org/asp-getdrive-method/)

ASP 中的**获取驱动方法用于返回对应于指定路径中驱动器的驱动对象。这是一个预定义的 ***文件系统*** 对象的方法。**

**语法:**

```vb
FileSystemObject.GetDrive(drivespec) 
```

**参数值:**

*   **Driving specification:** Required attribute. It can be the drive letter (c), the drive letter with colon (c:), the drive letter with colon and path separator (c:), or any network sharing specification (\computer2\share1).

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
***Drive is: d***
```