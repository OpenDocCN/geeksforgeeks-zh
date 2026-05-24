# ASP CreateFolder()方法

> 原文:[https://www.geeksforgeeks.org/asp-createfolder-method/](https://www.geeksforgeeks.org/asp-createfolder-method/)

**ASP 创建文件夹方法** 用于在服务器中创建新的目录或文件夹。这是**文件系统**对象的预定义方法。它接受文件夹的名称作为参数。

**语法:**

```vb
FileSystemObject.CreateFolder( name ) 
```

**参数值:**这个方法接受如上所述的单个参数，如下所述:

*   **Name:** It specifies the name of the folder that must be newly created. This is a required parameter.

**示例代码:**本示例使用 CreateFolder()方法创建一个名为“hello”的新文件夹。

```vb
<%
dim fs,f
set fs = Server.CreateObject("Scripting.FileSystemObject")
set f = fs.CreateFolder("d:\hello")
set f = nothing
set fs = nothing
%>
```