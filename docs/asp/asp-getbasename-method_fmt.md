# ASP GetBaseName 方法

> 原文：[https://www.geeksforgeeks.org/asp-getbasename-method/](https://www.geeksforgeeks.org/asp-getbasename-method/)

ASP 中的 `GetBaseName` 方法用于从文件的指定位置返回文件或文件夹的基名称。这是一个预定义的 `FileSystemObject` 对象的方法。

例如，路径为 `d::/hello/GFG/sudo . ASP` 的文件的基本名称是 `sudo.asp`。

## 语法

```vb
FileSystemObject.GetBaseName(path)
```

## 参数值

`path`：是必选属性。它指定将为其返回 basename 的完整路径名。

## 示例

下面的例子说明了 ASP `GetBaseName` 方法。

### Javascript

```vb
<%
dim fs
set fs=Server.CreateObject("Scripting.FileSystemObject")
Response.Write(fs.GetBaseName("d:\Hello\sudo\GeeksForGeeks"))
set fs=nothing
%>
```

## 输出

```vb
GeeksForGeeks
```