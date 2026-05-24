# ASP 文本流。雅典脱机房产

> 原文:[https://www . geesforgeks . org/ASP-textstream-atendofline-property/](https://www.geeksforgeeks.org/asp-textstream-atendofline-property/)

**ASP 自动脱机属性**用于返回一个布尔值，该值指定文件指针是否位于文本流文件的行尾。如果文件指针位于行尾，则返回 true，否则返回 false。

**注意:**此属性仅适用于打开阅读的 TextStream 对象。

**语法:**

```vb
TextStreamObject.AtEndOfLine
```

**示例:**下面的代码说明了 ASP AtEndOfLine 属性。

## ASP

```vb
<%
dim fs,f,t,x
set fs=Server.CreateObject("Scripting.FileSystemObject")
set f=fs.CreateTextFile("d:\GFG.txt")
f.write("Hello GeeksForGeeks")
f.close

set t=fs.OpenTextFile("d:\GFG.txt",1,false)
do while t.AtEndOfLineG<>true
 x=t.Read(1)
loop
t.close
Response.Write("The last character im the line is: " & x)
%>
```

**输出:**

```vb
The last character in the line is s. 
```