# ASP 应用。静态对象集合

> 原文: [https://www.geeksforgeeks.org/asp-application-staticobjects-collection/](https://www.geeksforgeeks.org/asp-application-staticobjects-collection/)

应用。ASP 中的 static objects Collection 用于存储应用对象范围内所有使用 `<object>` 标签创建的对象。

**语法**

```vb
Application.StaticObjects( Key )
```

**参数值**

*   `key` : 必需的参数。它指定要检索的对象属性的名称。

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