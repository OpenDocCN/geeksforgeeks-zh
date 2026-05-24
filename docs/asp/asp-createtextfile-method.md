# ASP 创建文本文件方法

> 原文:[https://www.geeksforgeeks.org/asp-createtextfile-method/](https://www.geeksforgeeks.org/asp-createtextfile-method/)

**ASP 创建文本文件方法**用于在当前目录下创建一个新的文本文件，它返回一个文本流对象，该对象可用于读写文件的内容。

**语法:**

```vb
FileSystemObject.CreateTextFile(filename[,overwrite[,unicode]])
```

**参数值:**

*   **File name:** Specify the name of the newly created file.
*   **Overlay:** is an optional attribute. It contains a Boolean value indicating whether existing files can be overwritten. True means that the file can be overwritten, False means that the file cannot be overwritten. The default value is true.
*   **Unicode:** is an optional attribute. It contains a Boolean value indicating whether the file was created as a Unicode or ASCII file. If True, it means that the file was created as a Unicode file; if False, it means that the file was created as an ASCII file. The default value is false.

**示例:**下面的代码演示了 ASP 创建文本文件的方法。

## ASP

```vb
<%
dim fs,tfile
set fs=Server.CreateObject("Scripting.FileSystemObject")
set tfile=fs.CreateTextFile("e:\GeeksGFG.txt") 
tfile.WriteLine("Hello GeeksForGeeks!")
tfile.close
Response.write("File is closed")
set tfile=nothing
set fs=nothing
%>
```

**输出:**

```vb
File is closed
```