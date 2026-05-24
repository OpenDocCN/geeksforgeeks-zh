# ASP 词典。拆卸方法

> 原文:[https://www.geeksforgeeks.org/asp-dictionary-remove-method/](https://www.geeksforgeeks.org/asp-dictionary-remove-method/)

**ASP 词典。移除方法**用于从字典对象中移除指定的键值对。

**语法:**

```vb
DictionaryObject.Remove(key)
```

**参数值:**

*   **key:** Required attribute. It specifies the key-value pair to be deleted.

**示例代码:**

## ASP

```vb
<%
dim d,a,i
set d=Server.CreateObject("Scripting.Dictionary")
d.Add "m","mango"
d.Add "z","zebra"
d.Add "c","cat"

d.Remove("c")
Response.Write("
<p>Key values:</p>
")
a=d.Keys
for i=0 to d.Count-1
  Response.Write(a(i))
  Response.Write("<br>")
next

set d=nothing
%>
```

**输出:**

```vb
Key Values
m
z
```