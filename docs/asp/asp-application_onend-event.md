# ASP 应用 _OnEnd 事件

> 原文:[https://www.geeksforgeeks.org/asp-application_onend-event/](https://www.geeksforgeeks.org/asp-application_onend-event/)

***ASP Application_OnEnd 事件**发生在应用程序结束或退出后。它在会话结束时发生。因此，事件被放在全局文件中。这一切都可能在服务器停止工作时发生。*

**注意:**OnEnd 事件处理程序中唯一可用的内置 ASP 对象是服务器和应用程序。

***句法***

```vb
***<SCRIPT LANGUAGE=ScriptLanguage RUNAT=Server>***
***Sub Application_OnEnd. . . End Sub***
***</SCRIPT>***
```

**参数值**

*   **Script language:** Defines the script language for writing event scripts. It supports different scripting languages such as VBScript or JScript.

**示例代码:**

```vb
***<script Language="VBScript" RUNAT=Server>***
***Sub Application_OnEnd()***
 ***Calculate_Stats()***
***End Sub***

***Sub Application_OnStart()***
 ***Application("NumSession") = 0***
 ***Application("NumVisited") = 0***
***End Sub***

***Sub Session_OnEnd()***
 ***Application("NumSession") = Application("NumSession") - 1***
***End Sub***

***Sub Session_OnStart()***
 ***Application("NumSession") = Application("NumSession") + 1***
 ***Application("NumVisited") = Application("NumVisited") + 1***
***End Sub*** 
***</script>***

***-------------------File1.asp----------------------------***
***Response.Write "You are " & Application("NumSession") & " of " & Application("NumVisited") & " users."***
```