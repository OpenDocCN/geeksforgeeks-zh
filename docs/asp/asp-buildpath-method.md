# ASP 构建路径方法

> 原文:[https://www.geeksforgeeks.org/asp-buildpath-method/](https://www.geeksforgeeks.org/asp-buildpath-method/)

***ASP 构建路径方法是*** 用于向现有路径追加或添加文件名。它是文件系统对象的预定义方法。

**语法:**

```vb
[newpath=]FileSystemObject.BuildPath(path,name)
```

**参数值:**

*   Path: It specifies an existing path to which the file name will be appended.
*   Name: Specifies the file name that will be appended to the existing path.

***示例代码下面的代码演示了***

```vb
***<%***
***dim fs,path***
***set fs=Server.CreateObject("Scripting.FileSystemObject")***
***path=fs.BuildPath("d:\myfiles","hello")***
***response.write(path)***
***set fs=nothing***
***%>***
```

的账单路径方法

***<u>输出:</u>***

```vb
d:\myfiles\hello
```