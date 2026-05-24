# ASP 驱动属性

> 原文:[https://www.geeksforgeeks.org/asp-drive-property/](https://www.geeksforgeeks.org/asp-drive-property/)

**ASP 驱动器属性**用于返回指定文件或文件夹所在的驱动器号名称。

**语法:**

*   **对于文件对象:**

    ```vb
    FileObject.Drive
    ```

*   **对于文件夹对象:**

    ```vb
    FolderObject.Drive
    ```

以下示例演示了 **ASP 驱动**属性:

**示例 1:** 下面的代码演示了 ASP 文件。驱动属性。

## 动态服务器页面

```vb
<%
dim fs,f
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the given file
set f=fs.GetFile("d:\GFG.txt")

Response.Write("File resides on drive: ")

'Getting the drive where the file resides
Response.Write(f.Drive)

set f=nothing
set fs=nothing
%>
```

**输出:**

```vb
File resides on drive: d:
```

**示例 2:** 下面的代码演示了 ASP 文件夹。驱动属性。

## 动态服务器页面

```vb
<%
dim fs,fol
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the required folder
set fol=fs.GetFolder("D:\GFG")

'Getting the drive where the folder is stored
Response.Write("This folder is on drive " & fol.Drive)

'Getting another folder
set fol=fs.GetFolder("F:\Downloads")

'Getting the drive where the folder is stored
Response.Write("<br> This folder is on drive " & fol.Drive)

set fol=nothing
set fs=nothing
%>
```

**输出:**

```vb
This folder is on drive D:
This folder is on drive F:
```