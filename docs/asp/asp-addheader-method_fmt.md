# ASP 添加标题方法

> 原文: [https://www.geeksforgeeks.org/asp-addheader-method/](https://www.geeksforgeeks.org/asp-addheader-method/)

`ASP` 添加头方法用于指定为 HTTP 头添加一个新的名称，并为 HTTP 响应提供一个给定值。这是一个 `Response` 类型对象的方法。

*   一旦添加了标题，就无法删除。
*   除非你进行响应，否则在向客户端发送任何输出之前，必须调用此方法。缓冲区被设置为 `true`。

## 语法

```vb
response.AddHeader name, value
```

## 参数值

该方法接受两个参数，如上所述，如下所述:

*   **Name** : 定义新头变量的名称。名称不能包含任何下划线 (`_`)。
*   **Value** : 定义新头变量的初始值。

## 返回值

这个方法没有返回值。

## 例 1

```vb
<% Response.AddHeader "WARNING", "Error message text" %>
```

## 示例 2

下面的代码使用 `AddHeader` 方法请求客户端使用基本身份验证。

```vb
<% Response.AddHeader "WWW-Authenticate", "BASIC" %>
```

## 例 3

```vb
<% Response.AddHeader "CustomHeader", "CustomValue" %>
```

## 参考

[https://docs.microsoft.com/en-us/previous-versions/iis/6.0-sdk/ms524327(v=vs.90)](https://docs.microsoft.com/en-us/previous-versions/iis/6.0-sdk/ms524327(v=vs.90))