# ASP 内容集合

> 原文:[https://www.geeksforgeeks.org/asp-contents-collection/](https://www.geeksforgeeks.org/asp-contents-collection/)

**ASP 内容集合**用于通过脚本命令收集附加到应用对象的项目。该集合还可用于提供已被赋予应用范围的项目列表，

**内容。移除和内容。RemoveAll** 方法可用于从集合中移除部分或全部项目。

**语法** :

```vb
Application.Contents(Key) 

```

**参数值:**

*   **Key** : A key that contains a single value, that is, the name of the item.

**示例 1:** 我们使用来添加将要添加到内容集合中的名称和对象。

```vb
<%
Application("name")="GeeksForGeeks"
Set Application("objtest")=Server.CreateObject("ADODB.Connection")
%> 

```

**例 2:**

```vb
<%
Application("author")="GeeksforGeeks"
Application("Contributors")="Rahul Jain"

for each x in Application.Contents
 Response.Write(x & "=" & Application.Contents(x) & "<br>")
next
%>

```

**输出**

```vb
author=GeeksforGeeks
Contributors=Rahul Jain

```