# ASP GetFile 方法

> 原文:[https://www.geeksforgeeks.org/asp-getfile-method/](https://www.geeksforgeeks.org/asp-getfile-method/)

`GetFile` 方法在 ASP 中用于返回指定路径下文件对应的 `File` 对象。这是 `FileSystemObject` 的预定义方法。

## 语法

```vb
FileSystemObject.GetFile(path)
```

## 参数值

`path`：是必选属性。它指定文件的路径。

## 示例代码

下面的代码演示了 ASP `GetFile` 方法。

```vb
<%
dim fs,f
set fs=Server.CreateObject("Scripting.FileSystemObject")
set f=fs.GetFile("d:\sudo\hello.html")
Response.Write("The file was last modified on: ")
Response.Write(f.DateLastModified)
set f=nothing
set fs=nothing
%>
```

## 输出

```vb
The file was last modified on 01/01/20 4:23:56 AM
```