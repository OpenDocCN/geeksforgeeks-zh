# ASP 目录。拆卸方法

> 原文:[https://www.geeksforgeeks.org/asp-contents-remove-method/](https://www.geeksforgeeks.org/asp-contents-remove-method/)

**ASP 目录。移除方法**用于从*应用程序中移除项目。内容*收藏。它是应用程序类型对象的预定义方法，

**语法:**

```vb
Application.Contents.Remove(name|index)

```

**参数值**:包含值即 e 名称，代表将从应用程序中删除的指定项目的索引。

**返回值:Th** 是没有返回值的方法。

**示例:**下面的代码说明了如何从内容列表中删除第二项。

```vb
<%
Application("'name1")=("GeeksforGeeks")
Application("name2")=("Javatpoint")
Application("name3")=("Sanfoundary")
Application.Contents.Remove("name2")
for each x in Application.Contents
 Response.Write(x & "=" & Application.Contents(x) & "<br>")
next
%>

```

**输出**

```vb
name1=GeeksforGeeks
name3=Sanfoundary 

```