# ASP 存在方法

> 原文:[https://www.geeksforgeeks.org/asp-exists-method/](https://www.geeksforgeeks.org/asp-exists-method/)

**ASP Exists 方法**用于返回一个布尔值，如果指定的键存在，则返回 true，否则返回 false。

**语法:**

```vb
DictionaryObject.Exists(key)
```

**参数:**这个方法有一个如上所述的参数，下面讨论:

*   **Key:** It specifies the name of the key value to be searched in the dictionary.

**示例:**下面的代码演示了 ASP 字典。存在方法。

## ASP

```vb
<%
dim dict

'Create a new dictionary
set dict=Server.CreateObject("Scripting.Dictionary")

'Add values to the dictionary
dict.Add "g","geeks"
dict.Add "p","placements"
dict.Add "c","competitive"

'Check if the key exists in the dictionary
if dict.Exists("g")=true then
  Response.Write("The 'g' key exists in the dictionary")
else
  Response.Write("The 'g' key does not exist in the dictionary")
end if

Response.Write("<br>")

'Check for another key in the dictionary
if dict.Exists("m")=true then
  Response.Write("The 'm' key exists in the dictionary")
else
  Response.Write("The 'm' key does not exist in the dictionary")
end if

set dict=nothing
%>
```

**输出:**

```vb
The 'g' key exists in the dictionary
The 'm' key does not exist in the dictionary 
```