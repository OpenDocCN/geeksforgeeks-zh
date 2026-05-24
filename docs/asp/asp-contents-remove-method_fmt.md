# ASP Contents.Remove 方法

> 原文: [https://www.geeksforgeeks.org/asp-contents-remove-method/](https://www.geeksforgeeks.org/asp-contents-remove-method/)

`ASP Contents.Remove` 方法用于从 `Application` 对象的 `Contents` 集合中移除一个项目。它是 `Application` 类型对象的预定义方法。

## 语法

```vb
Application.Contents.Remove(name|index)
```

## 参数值

`name` 或 `index`，代表将从应用程序中删除的指定项目的名称或索引。

## 返回值

此方法没有返回值。

## 示例

下面的代码说明了如何从内容列表中删除第二项。

```vb
<%
Application("name1")=("GeeksforGeeks")
Application("name2")=("Javatpoint")
Application("name3")=("Sanfoundary")
Application.Contents.Remove("name2")
for each x in Application.Contents
 Response.Write(x & "=" & Application.Contents(x) & "<br>")
next
%>
```

## 输出

```vb
name1=GeeksforGeeks
name3=Sanfoundary
```