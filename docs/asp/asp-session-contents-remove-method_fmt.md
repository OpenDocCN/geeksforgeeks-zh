# ASP Session.Contents.Remove 方法

> 原文: [https://www.geeksforgeeks.org/asp-session-contents-remove-method/](https://www.geeksforgeeks.org/asp-session-contents-remove-method/)

`Session.Contents.Remove` 方法在 ASP 中用于从 `Session` 对象的 `Contents` 集合中移除项目。这是 `Session` 对象的一个预定义方法。

## 语法

```vb
Session.Contents.Remove(name | index)
```

## 参数值

它包含一个值，代表要从会话中删除的指定项目的索引或名称。

## 示例

下面的代码说明了如何从 `Session.Contents` 列表中删除第三项。

```vb
<%
Session("item1") = ("Geeks")
Session("item2") = ("For")
Session("item3") = ("Geeks")
Session("item4") = ("sudo")

Session.Contents.Remove(3)

for each x in Session.Contents
    Response.Write(x & "=" & Session.Contents(x) & "<br>")
next
%>
```

## 输出

```
item1= Geeks
item2=For
item4=Sudo
```