# ASP 服务器创建对象方法

> 原文: [https://www.geeksforgeeks.org/asp-server-createobject-method/](https://www.geeksforgeeks.org/asp-server-createobject-method/)

**ASP 服务器创建对象方法**用于创建服务器对象的实例。此方法创建的对象具有页面范围。当服务器完成当前 ASP 页面时，这些对象将被销毁。我们通常使用`Global.asa`文件中的`<对象>`标签在会话或应用程序中创建一个对象。

## 语法

```vb
Server.CreateObject(progID)
```

## 参数值

包含代表要创建的对象类型的值，即`progID`。程序标识的格式是`组件.`。

## 示例-1

下面的代码，用于创建一个对象。

```vb
<%
Set adrot=Server.CreateObject("MSWC.AdRotator")
%>
```

## 示例-2

下面的代码说明了我们无法创建与内置对象同名的对象。

```vb
<%
Set Application=Server.CreateObject("Application")
%>
```