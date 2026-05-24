# MS 接入中的 LCase()和 UCase()功能

> 原文:[https://www . geesforgeks . org/lcase-and-ucase-function in-ms-access/](https://www.geeksforgeeks.org/lcase-and-ucase-function-in-ms-access/)

**1。LCase()函数:**
在 MS Access 中，LCase()函数将文本从大写转换为小写。在这个函数中，一个字符串作为参数传递，结果它将以小写形式返回该字符串。

**语法:**

```sql
LCase(text)
```

**示例–**

```sql
SELECT LCASE("GeekForGeeks") 
AS LowercaseName
```

**输出–**

| 低级名称 |
| 极客们 |

**示例–**

```sql
SELECT LCASE("GFG") 
AS LowercaseName
```

**输出–**

| 低级名称 |
| gfg |

**2。UCase()函数:**
它的工作方式类似于 LCase()函数，但它将给定的字符串转换为大写。在这个函数中，将传递一个文本，它将以大写形式返回字符串。

**语法:**

```sql
UCase(text)
```

**示例–**

```sql
SELECT UCASE("GeekForGeeks") 
AS UppercaseName
```

**输出–**

| 高级用户名 |
| GEEKSFORGEEKS |

**示例–**

```sql
SELECT UCASE("gfg") 
AS UppercaseName
```

**输出–**

| 高级用户名 |
| GFG |