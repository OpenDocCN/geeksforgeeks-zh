# ASP 应用 _OnStart 事件

> 原文:[https://www . geesforgeks . org/ASP-application _ onstart-event/](https://www.geeksforgeeks.org/asp-application_onstart-event/)

**ASP Application_OnStart 事件**发生在用户创建的新会话开始之前。它发生在引用应用程序对象之前。此事件将放在 Global.asa 文件中。当引用会话对象、请求对象或响应对象时，应用程序启动事件脚本会导致错误。

**语法:**

```vb
***<SCRIPT LANGUAGE=ScriptLanguage RUNAT=Server>***
***Sub Application_OnStart. . . End Sub***
***</SCRIPT>***
```

**参数值**

*   **Script language:** Defines the script language for writing event scripts. It supports different scripting languages such as VBScript or JScript.

**示例代码:下面的代码用于显示 ASP 文件中的访问者数量。**

**Global.asa**

**HTML 文件**

```vb
<***html>***
 ***<head>***
***</head>***
 ***<body>***
***<p>***
***There are <%response.write(Application("visitors"))%>***
***online now!***
***</p>***
***</body>***
```