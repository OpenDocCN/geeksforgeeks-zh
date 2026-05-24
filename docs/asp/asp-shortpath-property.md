# ASP 短路径属性

> 原文:[https://www.geeksforgeeks.org/asp-shortpath-property/](https://www.geeksforgeeks.org/asp-shortpath-property/)

**ASP 短路径属性**用于返回指定文件或文件夹的短路径。

**语法:**

*   **用于文件对象:**

    ```vb
    FileObject.ShortPath
    ```

*   **用于文件夹对象:**

    ```vb
    FolderObject.ShortPath
    ```

以下示例演示了 **ASP 短路径属性**。

**示例 1:** 下面的代码说明了 ASP 文件。短路径属性。

## ASP

```vb
<%
dim fs,f
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Get the file to be used
set f=fs.GetFile("D:\geeksforgeeksfolder\gfglongfilename.txt")

'Get the full path of the file
Response.Write("Full Path: " & f.Path)

'Get the short path of the file
Response.Write("<br>Short Path: " & f.ShortPath)

set f=nothing
set fs=nothing
%>
```

**输出:**

```vb
Full Path: D:\geeksforgeeksfolder\gfglongfilename.txt
Short Path: D:\GEEKSF~1\GFGLON~1.TXT
```

**示例 2:** 下面的代码说明了 ASP 文件夹。短路径属性。

## ASP

```vb
<%
dim fs,f
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the folder to be used
set f=fs.GetFolder("D:\geeksforgeeksfolder")

'Get the full path of the folder
Response.Write("Full Path: " & f.Path)

'Get the short path of the folder
Response.Write("<br>Short Path: " & f.ShortPath)

set f=nothing
set fs=nothing
%>
```

**输出:**

```vb
Full Path: D:\geeksforgeeksfolder
Short Path: D:\GEEKSF~1
```