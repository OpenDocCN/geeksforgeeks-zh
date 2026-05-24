# MS 接入中的 LTrim()和 RTrim()功能

> 原文:[https://www . geesforgeks . org/ltrim-and-rtrim-function in-ms-access/](https://www.geeksforgeeks.org/ltrim-and-rtrim-function-in-ms-access/)

**1。LTrim()函数:**
在 MS Access LTrim()函数中，删除给定字符串中的所有前导空格。在 LTrim()函数中，一个字符串将作为参数传递，它将返回不带前导空格的字符串。

**语法:**

```sql
LTrim(string)
```

**示例-1 :**

```sql
SELECT LTrim("    GEEKSFORGEEKS") AS LeftTrimmedString;
```

**输出–**

| **笔译摘要** |
| GEEKSFORGEEKS |

**示例-2 :**

```sql
SELECT LTrim("    GFG") AS LeftTrimmedString;
```

**输出–**

| **笔译摘要** |
| GFG |

**2。RTrim()函数:**
它的工作原理与 LTrim()函数相同，但它将删除字符串中的所有尾随空格。

**语法:**

```sql
RTrim(string)
```

**示例-1 :**

```sql
SELECT RTrim("GEEKSFORGEEKS    ") AS RightTrimmedString;
```

**输出–**

| **右修剪字符串** |
| GEEKSFORGEEKS |

**示例-2 :**

```sql
SELECT RTrim("GFG    ") AS RightTrimmedString;
```

**输出–**

| **右修剪字符串** |
| GFG |