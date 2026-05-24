# ASP 路径属性

> 原文: [https://www.geeksforgeeks.org/asp-path-property/](https://www.geeksforgeeks.org/asp-path-property/)

`ASP 路径属性`用于获取系统上指定文件、文件夹或驱动器的完整路径。

**语法:**

*   对于文件对象：
    ```vb
    FileObject.Path
    ```

*   对于文件夹对象：
    ```vb
    FolderObject.Path
    ```

*   对于驱动对象：
    ```vb
    DriveObject.Path
    ```

以下示例演示了 `ASP 路径属性`。

## 示例 1：文件路径属性

下面的代码说明了 ASP 文件的 `Path` 属性。

```vb
<%
dim fs,f
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the given file
set f=fs.GetFile("d:\GFG\sudo\geeks.asp")

'Getting the path of the file
Response.Write("Complete path for the specified file: " & f.Path)

set f=nothing
set fs=nothing
%>
```

**输出:**

```vb
Complete path for the specified file: d:\GFG\sudo\geeks.asp
```

## 示例 2：文件夹路径属性

下面的代码说明了 ASP 文件夹的 `Path` 属性。

```vb
<%
dim fs,fol
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the required folder
set fol=fs.GetFolder("d:\GFG\geeks")

'Getting the complete path of the folder
Response.Write("The path of the folder is " & fol.Path)

set fol=nothing
set fs=nothing
%>
```

**输出:**

```vb
The path of the folder is D:\GFG\geeks
```

## 示例 3：驱动路径属性

下面的代码说明了 ASP 驱动的 `Path` 属性。

```vb
<%
dim fs,drive
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Get the required drive
set drive=fs.GetDrive("d:")

'Finding the path of the drive
Response.Write("The path of the drive is: " & drive.Path)

set drive=nothing
set fs=nothing
%>
```

**输出:**

```vb
The path of the drive is: D:
```