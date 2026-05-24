# ASP 获取特殊文件夹方法

> 原文:[https://www.geeksforgeeks.org/asp-getspecialfolder-method/](https://www.geeksforgeeks.org/asp-getspecialfolder-method/)

**ASP 获取特殊文件夹方法**用于返回对指定特殊文件夹的引用。

**语法:**

```vb
FileSystemObject.GetSpecialFolder(foldername) 
```

**参数值**

**文件夹名称:**必选属性。它指定要返回的特殊文件夹的名称。它包含一个介于 0 和 2 之间的数值，代表三种不同类型的文件夹，如下所示。

*   **0** = Windows folder-contains files installed by Windows operating system.
*   **1** = System folder-contains libraries, fonts and device drivers.
*   [T0】 2 = temporary folder--used to store temporary files.

**示例:**下面的代码演示了 ASP GetSpecialFolder 方法。

## ASP

```vb
<%
dim fs,p
set fs=Server.CreateObject("Scripting.FileSystemObject")
set p=fs.GetSpecialFolder(1)
Response.Write(p)
set p=nothing
set fs=nothing
%>
```

**输出:**

```vb
C:\WINNT\system32
```