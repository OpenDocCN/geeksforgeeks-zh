# ASP `DateCreated` 属性

> 原文：[https://www.geeksforgeeks.org/asp-datecreated-property/](https://www.geeksforgeeks.org/asp-datecreated-property/)

`ASP DateCreated` 属性用于返回给定文件在系统上创建的日期和时间。

**语法：**

*   用于文件对象：
    ```vb
    FileObject.DateCreated
    ```

*   用于文件夹对象：
    ```vb
    FolderObject.DateCreated
    ```

以下示例演示了 `ASP DateCreated` 属性。

## 示例 1：演示文件对象的 `DateCreated` 属性

下面的代码演示了 ASP 文件的 `DateCreated` 属性。

```vb
<%
dim fs,f
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the file
set f=fs.GetFile("d:\GFG.txt")
Response.Write("File created on: ")

'Getting the date that the file was created
Response.Write(f.DateCreated)
set f=nothing
set fs=nothing
%>
```

**输出：**

```vb
File created on: 3/4/2020 10:07:20 AM
```

## 示例 2：演示文件夹对象的 `DateCreated` 属性

下面的代码演示了 ASP 文件夹的 `DateCreated` 属性。

```vb
<%
dim fs,fol
set fs=Server.CreateObject("Scripting.FileSystemObject")

'Getting the folder
set fol=fs.GetFolder("d:\GFG")
Response.Write("This folder was created on: ")

'Getting the date when the folder was created
Response.Write(fol.DateCreated)

set fol=nothing
set fs=nothing
%>
```

**输出：**

```vb
This folder was created on: 12-03-2021 12:54:29 
```