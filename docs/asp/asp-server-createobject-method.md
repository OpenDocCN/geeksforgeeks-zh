# ASP 服务器创建对象方法

> 原文:[https://www . geesforgeks . org/ASP-server-createobject-method/](https://www.geeksforgeeks.org/asp-server-createobject-method/)

**ASP 服务器创建对象方法**用于创建服务器对象的实例。此方法创建的对象具有页面范围。当服务器完成当前 ASP 页面时，这些对象将被销毁。我们通常使用 **Global.asa** 文件中的 **<对象>标签**在会话或应用程序中创建一个对象。

**语法:**

```vb
Server.CreateObject(progID) 
```

**参数值:**包含代表要创建的对象类型的值，即**。程序标识的格式是组件。**

****示例-1:** 下面的代码，用于创建一个对象。**

## **ASP**

```vb
<%
Set adrot=Server.CreateObject("MSWC.AdRotator")
%>
```

****示例-2:** 下面的代码说明了我们无法创建与内置对象同名的对象。**

## **ASP**

```vb
<%
Set Application=Server.CreateObject("Application")
%>
```