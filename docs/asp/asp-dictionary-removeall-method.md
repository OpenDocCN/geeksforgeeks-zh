# ASP 词典。移除所有方法

> 原文:[https://www . geesforgeks . org/ASP-dictionary-remove all-method/](https://www.geeksforgeeks.org/asp-dictionary-removeall-method/)

**ASP 词典。移除所有方法**用于从字典对象中移除所有键值对。

**语法:**

```vb
DictionaryObject.RemoveAll
```

**示例代码:**下面的代码演示了 ASP 字典。移除所有方法。

## ASP

```vb
<%
dim d,a,i
set d=Server.CreateObject("Scripting.Dictionary")
d.Add "m","mango"
d.Add "n","naman"
d.Add "b",""banana>")
next

set d=nothing
%>
```

**输出:**

```vb
Key values:

(nothing)
```