# ASP write blankline 方法

> 原文:[https://www.geeksforgeeks.org/asp-writeblanklines-method/](https://www.geeksforgeeks.org/asp-writeblanklines-method/)

**ASP 写空白行方法**用于向文本文件中写入指定数量的新行字符。它是文本流对象的内置方法。

**语法:**

```vb
TextStreamObject.WriteBlankLines(numlines)
```

**参数值:**

*   **numchar:** Required attribute. It contains a numeric value that specifies the number of new line characters to be written to the text file.

**示例代码:**下面的代码说明了**ASP write blankline 方法。**

## ASP

```vb
<%
dim fs,f
set fs=Server.CreateObject("Scripting.FileSystemObject")
set f=fs.CreateTextFile("d:\GFG.txt",true)
f.WriteLine("Hello GeeksForGeeks")
f.WriteBlankLines(2)
f.WriteLine("A computer Science portal for Geeks")
f.close
set f=nothing
set fs=nothing
%>
```

**输出:**

```vb
Hello GeeksForGeeks

A computer science portal for Geeks
```