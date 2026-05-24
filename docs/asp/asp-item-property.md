# ASP 项目属性

> 原文:[https://www.geeksforgeeks.org/asp-item-property/](https://www.geeksforgeeks.org/asp-item-property/)

**ASP 项属性**用于返回或设置字典对象中某项的值。

**语法:**

```vb
DictionaryObject.Item(key)[=newitem]
```

**参数值:**

*   **Key:** Specifies the key associated with the project. is a required attribute.
*   **newitem:** It specifies the new item that must be set for the given key.

**示例:**下面的代码演示了 ASP 字典。项目属性。

## ASP

```vb
<%
Dim dict

'Create a new dictionary
Set dict=Server.CreateObject("Scripting.Dictionary")

'Add values to the dictionary
dict.Add "g","green"
dict.Add "r","red"
dict.Add "p","purple"

'Getting a value from the dictionary
Response.Write("Value of key 'p' is: " & dict.Item("p"))

'Setting a new value to the key
dict.Item("p") = "violet"

'Getting the value again from the dictionary
Response.Write("<br>Value of key 'p' is: " & dict.Item("p"))
%>
```

**输出:**

```vb
Value of key 'p' is: purple
Value of key 'p' is: violet
```