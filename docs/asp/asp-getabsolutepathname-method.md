# ASP GetAbsolutePathName 方法

> 原文:[https://www . geesforgeks . org/ASP-getabsolutepathname-method/](https://www.geeksforgeeks.org/asp-getabsolutepathname-method/)

ASP 中的 ***GetAbsolutePathName 方法*** 用于返回从根目录开始的完整完整路径。这是**文件系统**对象的内置方法。

**语法**

```vb
FileSystemObject.GetAbsolutePathName(path) 
```

**参数值**

*   ***Path:*** is a required attribute. It contains a string value that specifies an incomplete path that will be changed to a full path.

**示例:**下面的示例演示了 GetAbsolutePathName 方法。

## ASP

```vb
<%
dim gfg,path
set gfg=Server.CreateObject("Scripting.FileSystemObject")
path=gfg.GetAbsolutePathName("d:")
response.write("The Complete path is " + path)
%>
```

***输出:***

```vb
d:\Hello\GFG\sudo.txt
```