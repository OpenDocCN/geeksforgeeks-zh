# MS 接入中的左()和右()功能

> 原文:[https://www . geesforgeks . org/左右-功能-in-ms-access/](https://www.geeksforgeeks.org/left-and-right-function-in-ms-access/)

**1。左()函数:**
在 MS Access 中，左()函数从字符串的左边提取字符串。在左()函数中，将传递字符串和字符串的编号。它将从字符串的左边返回大小为传递号的字符串。

**语法:**

```sql
Left(string, number_of_chars)
```

**示例-1 :**

```sql
SELECT Left("GEEKSFORGEEKS", 3) AS ExtractString;
```

**输出–**

| **提取字符串** |
| 哇；哎呀 |

**示例-2 :**

```sql
SELECT Left("GEEKSFORGEEKS", 10) AS ExtractString;
```

**输出–**

| **提取字符串** |
| GEEKSFORGE& |

**2。Right()函数:**
Right()函数的工作方式与 Left()函数类似，但它从字符串的右端提取字符串。在这种情况下，将提取的字符串和字符串大小将作为参数传递。

**语法:**

```sql
Right(string, number_of_chars)
```

**示例-1 :**

```sql
SELECT Right("GEEKSFORGEEKS", 4) AS ExtractString;
```

**输出–**

| **提取字符串** |
| EEKS |

**示例-2 :**

```sql
SELECT Right("GEEKSFORGEEKS", 8) AS ExtractString;
```

**输出–**

| **提取字符串** |
| 对于极客来说 |