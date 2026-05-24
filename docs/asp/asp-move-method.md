# ASP 移动()方法

> 原文:[https://www.geeksforgeeks.org/asp-move-method/](https://www.geeksforgeeks.org/asp-move-method/)

**ASP 移动方法**用于将指定的文件或文件夹移动到给定的目的地。

**语法:**

*   **对于文件对象:**

    ```vb
    FileObject.Move(destination)
    ```

*   **对于文件夹对象:**

    ```vb
    FolderObject.Move(destination)
    ```

**参数:**该方法有一个参数，如上所述，讨论如下:

*   **目的地:**它指定文件或文件夹将被移动到的目的地。它不允许通配符。这是必需的参数。

下面的例子演示了 **ASP 移动方法**。

**示例 1:** 下面的代码演示了 ASP 文件。移动方法。

## 动态服务器页面

```vb
<%
dim fs,f,ts
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the file to be copied
set f=fs.GetFile("d:\GFG.txt")

'Reading the contents of the file
set ts=f.OpenAsTextStream(1)
Response.Write("Original File Content: " & ts.ReadAll)
ts.Close

'Moving the file to the given path
f.Move("d:\newfolder\GFG.txt")

Response.write("<br>" & "File is Moved!" & "<br>")

'Getting the moved file
set f=fs.GetFile("d:\newfolder\GFG.txt")

'Reading the contents of the moved file
set ts=f.OpenAsTextStream(1)
Response.Write("Moved File Content: " & ts.ReadAll)
ts.Close

set f=nothing
set fs=nothing
%>
```

**输出:**

```vb
Original File Content: This is an example file
File is Moved!
Moved File Content: This is an example file
```

**示例 2:** 下面的代码演示了 ASP 文件夹。移动方法。

## 动态服务器页面

```vb
<%
dim fs,f,ts
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the folder to be copied
set f=fs.GetFolder("d:\GFG")

'Moving the folder to the given path
f.Move("d:\newfolder\GFG")

Response.write("Folder is Moved!")

'Getting the moved folder
set f=fs.GetFolder("d:\newfolder\GFG")

Response.write("<br>" & "Folder successfully accessed")

set f=nothing
set fs=nothing
%>
```

**输出:**

```vb
Folder is Moved!
Folder successfully accessed
```