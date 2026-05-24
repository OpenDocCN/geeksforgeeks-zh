# ASP 会话 StaticObjects 集合

> 原文：[https://www.geeksforgeeks.org/asp-session-staticobjects-collection/](https://www.geeksforgeeks.org/asp-session-staticobjects-collection/)

ASP 中的 `StaticObjects` 集合用于存储会话对象范围内所有使用 `<object>` 标签创建的对象。

## 语法

```vb
Session.StaticObjects( Key )
```

**参数值**

*   `key`：必需。指定要检索的对象属性的名称。

## 示例

```html
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