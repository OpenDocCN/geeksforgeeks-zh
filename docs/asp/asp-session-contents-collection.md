# ASP 会话。内容收集

> 原文:[https://www . geesforgeks . org/ASP-session-contents-collection/](https://www.geeksforgeeks.org/asp-session-contents-collection/)

T2 会议。内容收集用于通过脚本命令收集附加到应用对象的项目。此集合还可用于提供给定会话范围的项目列表，

我们可以使用 [**目录。删除**](https://www.geeksforgeeks.org/asp-session-contents-remove-method/)****[**内容。移除所有方法**](https://www.geeksforgeeks.org/asp-session-contents-removeall-method/) 从集合中移除部分或全部项目。****

******语法:******

```vb
**Session.Contents(Key)** 
```

******参数值:******

*****   **key:** contains a single value, that is, the key representing the project name.****

******示例-1:** 我们过去常常添加将要添加到内容集合中的名称和对象。****

## ****动态服务器页面****

```vb
**<%
Session("name")="Hege"
Set Session("objtest")=Server.CreateObject("ADODB.Connection")
%>**
```

******示例-2:******

## ****ASP****

```vb
**<%
Session("Name")="Akku"
Session("Favourite Gane")="Cricket"

for each x in Session.Contents
 Response.Write(x & "=" & Session.Contents(x) & "<br>")
next
%>**
```

******输出:******

```vb
**Name = Akku 
Favourite Game = Cricket** 
```