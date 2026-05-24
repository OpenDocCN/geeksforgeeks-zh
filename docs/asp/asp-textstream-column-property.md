# ASP 文本流。列属性

> 原文:[https://www . geesforgeks . org/ASP-textstream-column-property/](https://www.geeksforgeeks.org/asp-textstream-column-property/)

**ASP 列属性**用于返回文本流文件中当前字符位置的列号。它是只读属性。

**注意:**在写入换行符之后(甚至在写入任何其他字符之前)，该属性为 1。

**语法:**

```vb
TextStreamObject.Column
```

**示例代码:**下面的代码说明了 ASP 列属性

## ASP

```vb
<%
dim gfg,f,t,x,y
set gfg=Server.CreateObject("Scripting.FileSystemObject")
set f=gfg.CreateTextFile("d:\GFG.txt")   // creating a File
f.write("Hello GeeksForGeeks")
f.close
  // opening a file
set t=gfg.OpenTextFile("d:\GFG.txt",1,false)
do while t.AtEndOfStream<>true
 x=t.Read(1)
 y=t.Column-1
loop
t.close
Response.Write("The last character in the text file is: " & x)
Response.Write("<br> at character position: " & y)
%>
```

**输出:**

```vb
The last character in the text file is: s
at character position: 19
```