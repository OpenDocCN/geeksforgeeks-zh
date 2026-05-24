# ASP GetParentFolderName 方法

> 原文:[https://www . geesforgeks . org/ASP-getparentfoldername-method/](https://www.geeksforgeeks.org/asp-getparentfoldername-method/)

ASP 中的 ***GetParentFolderName 方法*** 用于返回一个字符串值，该字符串值表示指定路径中最后一个组件的父文件夹的名称。它是文件系统对象的预定义方法。

**语法:**

```vb
***FileSystemObject.GetParentFolderName(path)*** 
```

***参数值:***

***路径:*** 必选属性。它指定要返回其父文件夹名称的完整路径文件或文件夹。

**示例代码:**下面的示例演示了 ASP GetParentFolderName 方法。

## ASP

```vb
<%
dim fs,p
set fs=Server.CreateObject("Scripting.FileSystemObject")
p=fs.GetParentFolderName("d:\sudo\GFG\Geeks.asp")
Response.Write(p)
set fs=nothing
%>
```

**输出:**

```vb
***d:\sudo\GFG***
```