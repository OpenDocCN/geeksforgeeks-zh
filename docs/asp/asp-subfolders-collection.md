# ASP 子文件夹集合

> 原文:[https://www.geeksforgeeks.org/asp-subfolders-collection/](https://www.geeksforgeeks.org/asp-subfolders-collection/)

**ASP 子文件夹集合**用于返回指定文件夹中所有子文件夹的集合。

**语法:**

```vb
FolderObject.SubFolders
```

**示例:**下面的代码演示了 ASP 文件夹。子文件夹集合。

## ASP

```vb
<%
dim fs,fo,x
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Get the folder to be read
set fo=fs.GetFolder("d:\GFG\")

'Loop through the subfolders in the folder
for each x in fo.SubFolders
  'Print the name of all subfolders in the GFG folder
  Response.write("Subfolder Name: " & x.Name & "<br>")
next

set fo=nothing
set fs=nothing
%>
```

**输出:**

```vb
Subfolder Name: html
Subfolder Name: css
Subfolder Name: asp
Subfolder Name: vbscript
```