# ASP GetDriveName 方法

> 原文:[https://www.geeksforgeeks.org/asp-getdrivename-method/](https://www.geeksforgeeks.org/asp-getdrivename-method/)

***ASP GetDriveName 方法*** 用于返回一个字符串值，该字符串值指定指定路径的驱动器名称。这是文件系统对象的预定义方法 ***。***

***句法***

```vb
FileSystemObject.GetDriveName(path) 
```

***参数值***

***路径:*** 是必选属性。它指定驱动器名返回的文件的完整路径。

**示例 1:** 下面的代码演示了 ASP GetDriveName 方法。

## Javascript

```vb
<%
dim fs,dname
set fs=Server.CreateObject("Scripting.FileSystemObject")
dname=fs.GetDriveName("d:\hello\sudo.html")
Response.Write(dname)
set fs=nothing
%>
```

**输出:**

```vb
d
```

**例二:**

## Javascript

```vb
<%
dim fs,dname
set fs=Server.CreateObject("Scripting.FileSystemObject")
dname=fs.GetDriveName("C:\inetpub\wwwroot\asptest\GFG.txt")
Response.Write(dname)
set fs=nothing
%>
```

**输出:**

```vb
c
```