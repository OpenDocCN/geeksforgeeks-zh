# ASP 文件收集

> 原文:[https://www.geeksforgeeks.org/asp-files-collection/](https://www.geeksforgeeks.org/asp-files-collection/)

**ASP 文件集合**用于返回指定文件夹中所有文件的集合。这些可以通过循环来获得单个文件的细节。

**语法:**

```vb
FolderObject.Files
```

**示例:**下面的代码演示了 ASP 文件。文件集合。

## ASP

```vb
<%
dim fs,fo,x
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Get the folder to be read
set fo=fs.GetFolder("d:\geeks\")

'Loop through the files present in the folder
for each x in fo.files
  'Print the name of the file
  Response.write("Filename: " & x.Name & "<br>")
next

set fo=nothing
set fs=nothing
%>
```

**输出:**

```vb
Filename: GFG_adv.txt
Filename: sudo.txt
Filename: ram.txt
Filename: shyam.txt
```