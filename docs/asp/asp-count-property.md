# ASP 计数属性

> 原文:[https://www.geeksforgeeks.org/asp-count-property/](https://www.geeksforgeeks.org/asp-count-property/)

**ASP 计数属性**用于返回字典对象中当前存在的键值对的数量。

**语法:**

```vb
DictionaryObject.Count
```

**示例:**下面的代码演示了 ASP 字典。计数属性。

## ASP

```vb
<%
dim dict

'Create a new dictionary
set dict=Server.CreateObject("Scripting.Dictionary")

'Add values to the dictionary
dict.Add "p","physics"
dict.Add "c","chemistry"
dict.Add "m","maths"

'Count the number of key-value pairs
Response.Write("Current number of entries: " & dict.Count)

'Add one more value
dict.Add "b","biology"

'Count the number of key-value pairs again
Response.Write("<br>Current number of entries: " & dict.Count)

set dict=nothing
%>
```

**输出:**

```vb
Current number of entries: 3
Current number of entries: 4
```