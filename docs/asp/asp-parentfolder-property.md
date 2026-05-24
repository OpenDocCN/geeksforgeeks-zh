# ASP 父文件夹属性

> 原文:[https://www.geeksforgeeks.org/asp-parentfolder-property/](https://www.geeksforgeeks.org/asp-parentfolder-property/)

**ASP 父文件夹属性**用于返回指定文件或文件夹的父文件夹的完整路径。

**语法:**

*   **用于文件对象:**

    ```vb
    FileObject.ParentFolder
    ```

*   **用于文件夹对象:**

    ```vb
    FolderObject.ParentFolder
    ```

以下示例说明了 **ASP 父文件夹属性**。

**示例 1:** 下面的代码演示了文件。父文件夹属性。

## ASP

```vb
<%
dim fs,f
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the given file
set f=fs.GetFile("d:\GFG\sudo\test.asp")

Response.Write("The file test.asp is in the folder: ")

'Getting the parent folder of the file
Response.Write(f.ParentFolder)

set f=nothing
set fs=nothing
%>
```

**输出:**

```vb
The file test.asp is in the folder: d:\GFG\sudo
```

**示例 2:** 下面的代码演示了文件夹。父文件夹属性。

## ASP

```vb
<%
dim fs,fol
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the given folder
set fol=fs.GetFolder("D:\GFG\sudo")

Response.Write("The 'sudo' folder is in the folder: ")

'Getting the parent folder of the file
Response.Write(fol.ParentFolder)

set fol=nothing
set fs=nothing
%>
```

**输出:**

```vb
The 'sudo' folder is in the folder: D:\GFG
```