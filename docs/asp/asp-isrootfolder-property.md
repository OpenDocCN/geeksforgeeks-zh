# ASP IsRootFolder 属性

> 原文:[https://www.geeksforgeeks.org/asp-isrootfolder-property/](https://www.geeksforgeeks.org/asp-isrootfolder-property/)

**ASP IsRootFolder 属性**返回一个布尔值，表示指定的文件夹是否是根文件夹。true 值表示它是根文件夹，false 值表示它不是根文件夹。

**语法:**

```vb
FolderObject.IsRootFolder
```

**示例:**下面的代码演示了 ASP IsRootFolder 属性。

## ASP

```vb
<%
dim fs,fo
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the required folder
set fo=fs.GetFolder("d:\GFG")

'Check if it is a root folder
Response.Write("IsRootFolder: " & fo.IsRootFolder)

'Getting another folder
set fo=fs.GetFolder("d:\")

'Check if it is a root folder
Response.Write("<br>IsRootFolder: " & fo.IsRootFolder)

set fo=nothing
set fs=nothing
%>
```

**输出:**

```vb
IsRootFolder: False
IsRootFolder: True
```