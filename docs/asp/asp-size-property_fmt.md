# ASP 尺寸属性

> 原文：[https://www.geeksforgeeks.org/asp-size-property/](https://www.geeksforgeeks.org/asp-size-property/)

**ASP 大小属性**用于返回指定文件或文件夹的大小。它以字节为单位返回值。

**语法：**

*   对于文件对象：
    ```vb
    FileObject.Size
    ```

*   对于文件夹对象：
    ```vb
    FolderObject.Size
    ```

## 示例-1：返回文件的大小

下面的代码返回文件的大小。

```vb
<%
dim fs,f
set fs=Server.CreateObject("Scripting.FileSystemObject")
set f=fs.GetFile("d:\GFG.asp")
Response.Write("The size of GFG.asp is: ")
Response.Write(f.Size & " bytes.")
set f=nothing
set fs=nothing
%>
```

**输出：**

```vb
The size of GFG.asp is: 100323 bytes.
```

## 示例-2：返回文件夹的大小

下面的代码返回一个文件夹的大小。

```vb
<%
dim fs,fo
set fs=Server.CreateObject("Scripting.FileSystemObject")
set fo=fs.GetFolder("d:\GFG")
Response.Write("The size of the folder test is: ")
Response.Write(fo.Size & " bytes.")
set fo=nothing
set fs=nothing
%>
```

**输出：**

```vb
The size of the folder test is: 123456 bytes.
```