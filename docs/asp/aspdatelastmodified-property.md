# ASPDateLastModified 属性

> 原文:[https://www.geeksforgeeks.org/aspdatelastmodified-property/](https://www.geeksforgeeks.org/aspdatelastmodified-property/)

**ASP DateLastModified 属性**用于获取特定文件或文件夹上次在系统上修改或更新的日期和时间。

**语法:**

*   **is the file object:**

```vb
FileObject.DateLastModified 
```

*   **is the folder object:**

```vb
FolderObject.DateLastModified
```

**示例-1:** 下面的代码演示了 ASP 文件。日期上次修改属性。

## ASP

```vb
<%
dim gfg,f
set gfg=Server.CreateObject("Scripting.FileSystemObject")
set f=gfg.GetFile("c:\test.txt")
Response.Write("File was last modified on: ")
Response.Write(f.DateLastModified)
set f=nothing
set gfg=nothing
%>
```

**输出:**

```vb
File last modified on: 1/10/2020 10:01:19 AM
```

**示例-2:** 下面的代码演示了 ASP 文件夹。日期上次修改属性。

## ASP

```vb
<%
dim gfg,fo
set gfg=Server.CreateObject("Scripting.FileSystemObject")
set fo=gfg.GetFolder("d:\GFG")
Response.Write("Folder last modified on: ")
Response.Write(fo.DateLastModified)
set fo=nothing
set gfg=nothing
%>
```

**输出:**

```vb
Folder last modified on: 1/10/2020 10:01:19 AM
```