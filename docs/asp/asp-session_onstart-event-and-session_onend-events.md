# ASP 会话 _ 开始事件和会话 _ 结束事件

> 原文:[https://www . geesforgeks . org/ASP-session _ onstart-event-and-session _ onend-events/](https://www.geeksforgeeks.org/asp-session_onstart-event-and-session_onend-events/)

当会话开始时，出现 **ASP 会话 _OnStart 事件**。它在服务器创建会话对象时发生。本次活动在**环球网**档案中进行。

当会话结束或关闭时，会出现 **ASP Session_OnEnd 事件**。当放弃的方法被调用并且会话超时时间结束时，就会发生这种情况。该事件发生在 Global.asa 文件上。

**语法:**

```vb
<SCRIPT LANGUAGE=ScriptLanguage RUNAT=Server>
Sub Session_OnStart
. . .  
End Sub
</SCRIPT>
```

**参数值:**

*   ***脚本语言:*** 它定义了用于编写事件脚本的脚本语言。它支持不同的脚本语言，如 VBScript 或 JScript。

**示例:**下面的代码用于显示 ASP 文件中的访问者数量。

## Global.asa

```vb
<script language="vbscript" runat="server">

Sub Application_OnEnd()
Application("totvisitors")=Application("visitors")
End Sub

Sub Application_OnStart
Application("visitors")=0
End Sub

Sub Session_OnStart
Application.Lock
Application("visitors")=Application("visitors")+1
Application.UnLock
End Sub

Sub Session_OnEnd
Application.Lock
Application("visitors")=Application("visitors")-1
Application.UnLock
End Sub

</script>
```

## index.asp

```vb
<html>
<head>
</head>
<body>

<p>
There are <%response.write(Application("visitors"))%>
online now!
</p>

</body>
</html>
```

**输出:**

```vb
There are online now!
```