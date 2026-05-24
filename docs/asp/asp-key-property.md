# ASP 密钥属性

> 原文:[https://www.geeksforgeeks.org/asp-key-property/](https://www.geeksforgeeks.org/asp-key-property/)

**ASP 键属性**用于将字典对象中现有的键值对更改为新的键值。

**语法:**

```vb
DictionaryObject.Key(key)=newkey 
```

**参数:**该方法有两个参数，如上所述，下面讨论:

*   **Key:** It specifies the name of the existing key that must be changed.
*   **newkey:** It defines the new name of the key. This is a required attribute.

**例:**

## ASP

```vb
<%
Dim dict

'Create a new dictionary
Set dict=Server.CreateObject("Scripting.Dictionary")

'Add values to the dictionary
dict.Add "m","mouse"
dict.Add "k","keyboard"
dict.Add "h","headphones"

'Change the key of one of pairs
dict.Key("h")="hd"

'Checking the new key
Response.Write("Value of changed key 'hd' is: " & dict.Item("hd"))
%>
```

**输出:**

```vb
"Value of changed key 'hd' is: headphones
```