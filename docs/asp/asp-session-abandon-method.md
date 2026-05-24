# ASP 会话放弃方法

> 原文:[https://www.geeksforgeeks.org/asp-session-abandon-method/](https://www.geeksforgeeks.org/asp-session-abandon-method/)

**ASP 会话。放弃方法**用于破坏用户的一个会话。通常，它会销毁存储在会话对象中的对象。如果我们不显式调用放弃方法，当会话超时时，服务器会销毁这些对象。

**注意:**调用此方法时，当前页面上的所有脚本处理完毕后，才删除当前 Session 对象。这意味着可以在调用放弃的同一页面上访问会话变量，但不能从另一个网页访问。

**语法**

```vb
***Session.Abandon*** 
```

**参数值:**此方法不包含任何值。

**返回值:**不返回值。

**例 1:**

```vb
<% 
Session.Abandon 
%>
```

**例 2:**

```vb
<%
Session("name")="Hello GeeksforGeeks"
Session.Abandon
Response.Write(Session("name"))
%>
```

**输出:**

```vb
Hello GeeksforGeeks
```