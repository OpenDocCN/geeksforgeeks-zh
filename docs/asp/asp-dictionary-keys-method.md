# ASP 词典。按键方法

> 原文:[https://www.geeksforgeeks.org/asp-dictionary-keys-method/](https://www.geeksforgeeks.org/asp-dictionary-keys-method/)

**ASP 词典。键方法**用于返回字典对象中所有键的数组。

**语法:**

```vb
DictionaryObject.Keys
```

**示例代码:**下面的代码演示了 ASP 键方法。

## ASP

```vb
<%
dim d,a,i
set d=Server.CreateObject("Scripting.Dictionary")
d.Add "m","mango"
d.Add "e","Elephant"
d.Add "n","Nagaland"

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
Key values:

m
e
n
```