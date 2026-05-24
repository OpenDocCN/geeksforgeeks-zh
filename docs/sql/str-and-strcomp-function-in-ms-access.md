# 移动台接入中的 Str()和 StrComp()功能

> 原文:[https://www . geesforgeks . org/str-and-str comp-function-in-ms-access/](https://www.geeksforgeeks.org/str-and-strcomp-function-in-ms-access/)

**1。Str()函数:**
在 MS Access 中，Str()函数返回一个字符串格式的数字。在这个函数中，我们可以传递函数将以字符串格式返回的任何数字。

**语法:**

```sql
 Str(number) 
```

**示例–**

```sql
SELECT Str(100) AS ConvertToString;
```

**输出–**

| **转换 ToString** |
| One hundred |

**示例–**

```sql
SELECT Str(421) AS ConvertToString;
```

**输出–**

| **转换 ToString** |
| Four hundred and twenty-one |

**2。函数的作用是:**
在 MS Access 中，函数比较两个字符串。它将采用两个参数 string1、string2 作为参数。如果两个字符串相同，则返回 0；如果第一个字符串大于第二个字符串，则返回 1；如果 string1 < string2，则返回-1；如果 string1 或 string2 为 null，则返回 null。

**语法:**

```sql
StrComp(string1, string2) 
```

**示例–**

```sql
SELECT StrComp("geeksforgeeks", "gfg") AS CompString;
```

**输出–**

| **压缩** |
| -1 |

**示例–**

```sql
SELECT StrComp("gfg", "geeksforgeeks") AS CompString;
```

**输出:**

| **压缩** |
| one |