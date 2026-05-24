# ASP 文本流。线路属性

> 原文:[https://www.geeksforgeeks.org/asp-textstream-line-property/](https://www.geeksforgeeks.org/asp-textstream-line-property/)

**ASP 文本流。行属性**是一个只读属性，可用于返回**文本流**文件中的当前行号。

**语法:**

```vb
TextStreamObject.Line 
```

**示例:**下面代码返回当前行号:

## ASP

```vb
<%
dim gfg,f,t
set gfg=Server.CreateObject("Scripting.FileSystemObject")
set f=gfg.CreateTextFile("d:\GFG.txt",true)
f.WriteLine("Hello GeeksForGeeks!")
f.WriteLine("A computer science portal for Geeks")
f.WriteLine("GFG is a Good platform tode!")
f.close

Set t=gfg.OpenTextFile("c:\test.txt",1)
do while t.AtEndOfStream=false
 Response.Write("Line " & t.Line & ": ")
 Response.Write(t.ReadLine)
 Response.Write("<br>")
loop
t.Close
%>
```

**输出:**

```vb
Line 1: Hello GeeksForGeeks!
Line 2: A computer science portal for geeks!
Line 3:  GFG is a Good Platform to code!
```