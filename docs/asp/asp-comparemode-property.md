# ASP 比较代码属性

> 原文:[https://www.geeksforgeeks.org/asp-comparemode-property/](https://www.geeksforgeeks.org/asp-comparemode-property/)

**ASP 比较代码属性**用于返回和设置数据比较模式，该模式比较字典对象中的键。数据比较模式可以有以下值。

*   **vbbinarycompare (0):** This specifies that binary comparison will be used for data.
*   [T0】 vbTextCompare(1): 【T1): This specifies that text comparison will be used for data.
*   **vbdatabasecopy (2):** Specifies that the data will be compared with the database.

**语法:**

```vb
DictionaryObject.CompareMode[=compare]
```

**参数:**该属性有一个参数如上所述，描述如下:

*   **Comparison:** is used to specify the comparison mode in the dictionary object. This is an optional parameter.

下面的例子演示了 ASP 字典。比较代码属性。

**例:**

## ASP

```vb
<%
dim dic

'Create a dictionary object
set dic=Server.CreateObject("Scripting.Dictionary")

'Set the comparison mode to be used
dic.CompareMode=1

'Add some key-value pairs to the dictionary
dic.Add "s","sudo"
dic.Add "c","competitive"

'Trying to add a new key that does not exists
dic.Add "p","placements"

Response.Write("The 'p' key-value was successfully added!")

'Trying to add a new key that already exists
'This will fail as the already exists!
dic.Add "c","code"

Response.Write("The 'c' key-value was successfully added!")
%>
```

**输出:**

```vb
The 'p' key-value was successfully added!
An error occurred on the server when processing the URL.
```