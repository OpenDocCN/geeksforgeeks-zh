# ASP GetAbsolutePathName 方法

> 原文: [https://www.geeksforgeeks.org/asp-getabsolutepathname-method/](https://www.geeksforgeeks.org/asp-getabsolutepathname-method/)

ASP 中的 `GetAbsolutePathName` 方法用于返回从根目录开始的完整路径。这是 `FileSystemObject` 对象的内置方法。

**语法**

```vb
FileSystemObject.GetAbsolutePathName(path) 
```

**参数值**

*   `Path:` 是一个必需的属性。它包含一个字符串值，用于指定将被转换为完整路径的不完整路径。

## ASP

下面的示例演示了 `GetAbsolutePathName` 方法。

```vb
<%
dim gfg,path
set gfg=Server.CreateObject("Scripting.FileSystemObject")
path=gfg.GetAbsolutePathName("d:")
response.write("The Complete path is " + path)
%>
```

## 输出

```vb
d:\Hello\GFG\sudo.txt
```