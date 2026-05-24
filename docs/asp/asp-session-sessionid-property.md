# ASP 会话。会话属性

> 原文:[https://www . geesforgeks . org/ASP-session-session id-property/](https://www.geeksforgeeks.org/asp-session-sessionid-property/)

***ASP 会话。SessionID 属性:*** 是只读属性，表示不能修改该属性。它为用户生成的每个新用户会话返回一个唯一的标识。每个会话都有一个唯一的标识，该标识是在创建会话时由服务器生成的。它作为 cookie 存储在客户端计算机中。

**语法:**

```vb
Session.SessionID  
```

**示例代码:**下面的代码返回会话的唯一标识。

## Javascript

```vb
<%
Response.Write(Session.SessionID)
%>
```

**输出:**

```vb
7464747834
```