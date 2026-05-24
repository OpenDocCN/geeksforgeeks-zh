# ASP 应用。静态对象集合

> 原文:[https://www . geesforgeks . org/ASP-application-static objects-collection/](https://www.geeksforgeeks.org/asp-application-staticobjects-collection/)

**应用。ASP 中的 static objects Collection**用于存储应用对象范围内所有使用 **<对象>** 标签创建的对象。

**语法**

```vb
Application.StaticObjects( Key )  
```

**参数值**

*   **key** : required parameter. It specifies the name of the property of the object to be retrieved.

**示例:**

## HTML

```vb
<object runat="server" 
        scope="session"
        id="MsgBoard" 
        progid="msgboard.MsgBoard">
</object>

<object runat="server" 
        scope="session"
        id="AdRot" 
        progid="MSWC.AdRotator">
</object>
```