# ASP 添加方法

> 原文:[https://www.geeksforgeeks.org/asp-add-method/](https://www.geeksforgeeks.org/asp-add-method/)

**ASP 词典。添加方法**用于向字典对象添加新的键值对。

**语法:**

```vb
DictionaryObject.Add(key, item)
```

**参数:**该方法有两个参数，如上所述，如下所述:

*   **Key:** Specify the name of the key to be inserted. is a required parameter.
*   **Item:** It specifies the value that must be associated with the key in the key-value pair.

**示例:**下面的代码演示了 ASP 字典。添加方法。

## ASP

```vb
Dim dict

'Create a new dictionary
Set dict=Server.CreateObject("Scripting.Dictionary")

'Add values to the dictionary
dict.Add "w","white"
dict.Add "b","blue"
dict.Add "br","Brown"
dict.Add "p","Pink"

'Retrieve some values from the dictionary
Response.Write("Value of key 'br' is: " & dict.Item("br"))
Response.Write("<br>Value of key 'p' is: " & dict.Item("p"))
%>
```

**输出:**

```vb
Value of key 'br' is: Brown
Value of key 'p' is: Pink
```