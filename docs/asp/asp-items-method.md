# ASP 项目法

> 原文:[https://www.geeksforgeeks.org/asp-items-method/](https://www.geeksforgeeks.org/asp-items-method/)

**ASP 项方法**用于返回字典对象中当前所有项的数组。

**语法:**

```vb
DictionaryObject.Items
```

**示例:**下面的代码演示了 ASP 字典。项目方法。

## ASP

```vb
<%
dim dict,arr,i
set dict=Server.CreateObject("Scripting.Dictionary")

'Add values to the dictionary
dict.Add "g","geeks"
dict.Add "c","coding" 
dict.Add "p","placements"

'Getting the items of the dictionary
arr=dict.Items

Response.Write("The values in the dictionary are:")

'Looping through the items
for i=0 to dict.Count-1
  Response.Write("<br> Value: " & arr(i))
next

set dict=nothing
%>
```

**输出:**

```vb
The values in the dictionary are:
Value: geeks
Value: coding
Value: placements
```