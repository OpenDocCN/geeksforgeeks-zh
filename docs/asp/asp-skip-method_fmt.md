# ASP 跳过法

> 原文:[https://www.geeksforgeeks.org/asp-skip-method/](https://www.geeksforgeeks.org/asp-skip-method/)

**ASP 跳过方法**用于在读取文本文件内容时跳过/忽略指定数量的字符。

**语法**

```vb
TextStreamObject.Skip(numchar)
```

**参数值**

*   `numchar`: 必需的属性。它指定在读取文本文件时要跳过的字符数。

**示例代码:** 下面的代码说明了 ASP 跳过方法。

## ASP 示例

```vb
<%
dim fs,f,t,x
set fs=Server.CreateObject("Scripting.FileSystemObject")
set f=fs.CreateTextFile("d:\GFG.txt")
f.write("Hello GeeksForGeeks")
f.close

set t=fs.OpenTextFile("d:\GFG.txt",1,false)
t.Skip(11)
x=t.ReadAll
t.close
Response.Write(x)
%>
```

**输出:**

```vb
ForGeeks
```