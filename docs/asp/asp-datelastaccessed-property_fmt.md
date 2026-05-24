# ASP 日期上次访问属性

> 原文：[https://www.geeksforgeeks.org/asp-datelastaccessed-property/](https://www.geeksforgeeks.org/asp-datelastaccessed-property/)

`ASP DateLastAccessed` 属性用于获取系统上最后一次访问特定文件或文件夹的日期和时间。

**语法：**

*   对于 `FileObject`：
    ```vb
    FileObject.DateLastAccessed
    ```

*   对于 `FolderObject`：
    ```vb
    FolderObject.DateLastAccessed
    ```

### 示例-1
下面的代码演示了 `FileObject.DateLastAccessed` 属性。

```vb
<%
dim fs,gfg
set fs=Server.CreateObject("Scripting.FileSystemObject")
set gfg=fs.GetFile("d:\GFG.txt")
Response.Write("File last accessed on: ")
Response.Write(gfg.DateLastAccessed)
set gfg=nothing
set fs=nothing
%>
```

**输出：**
```vb
File last accessed on: 12/29/2020 11:21:10 AM
```

### 示例-2
下面的代码演示了 `FolderObject.DateLastAccessed` 属性。

```vb
<%
dim fs,fo
set fs=Server.CreateObject("Scripting.FileSystemObject")
set fo=fs.GetFolder("d:\GFG")
Response.Write("Folder last accessed on: ")
Response.Write(fo.DateLastAccessed)
set fo=nothing
set fs=nothing
%>
```

**输出：**
```vb
Folder last accessed on: 12/29/2020 11:21:10 AM
```