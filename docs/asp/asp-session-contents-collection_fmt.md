# ASP 会话内容收集

> 原文：[https://www.geeksforgeeks.org/asp-session-contents-collection/](https://www.geeksforgeeks.org/asp-session-contents-collection/)

`Session.Contents` 集合用于通过脚本命令收集附加到 `Session` 对象的项目。此集合还可用于提供给定会话范围的项目列表。

我们可以使用 [`Session.Contents.Remove`](https://www.geeksforgeeks.org/asp-session-contents-remove-method/) 和 [`Session.Contents.RemoveAll`](https://www.geeksforgeeks.org/asp-session-contents-removeall-method/) 方法从集合中移除部分或全部项目。

**语法：**

```vb
Session.Contents(Key)
```

**参数值：**

*   `key`：包含一个值，即代表项目名称的键。

**示例-1：** 我们过去常常添加将要添加到内容集合中的名称和对象。

## 动态服务器页面

```vb
<%
Session("name")="Hege"
Set Session("objtest")=Server.CreateObject("ADODB.Connection")
%>
```

**示例-2：**

## ASP

```vb
<%
Session("Name")="Akku"
Session("Favourite Game")="Cricket"

for each x in Session.Contents
  Response.Write(x & "=" & Session.Contents(x) & "<br>")
next
%>
```

**输出：**

```vb
Name = Akku
Favourite Game = Cricket
```