# MS 接入中的 Mid()和 Len()功能

> 原文:[https://www . geesforgeks . org/mid-and-len-function-in-ms-access/](https://www.geeksforgeeks.org/mid-and-len-function-in-ms-access/)

**1。Mid()函数:**
在 MS Access 中，mid()函数将从给定的位置提取字符串。在这个函数中，将传递 3 个参数，第一个是字符串，第二个是字符串的起始位置，最后一个是字符串的长度。

**语法:**

```sql
Mid(string, start, length)

```

**示例-1 :**

```sql
SELECT Mid("GEEKSFORGEEKS", 3, 3) AS ExtractString;

```

**输出–**

| **提取字符串** |
| EKS |

**示例-2 :**

```sql
SELECT Mid("GEEKSFORGEEKS", 6, 14) AS ExtractString;

```

**输出–**

| **提取字符串** |
| 对于极客来说 |

**2。Len()函数:**
在 MS Access 中 Len()函数将返回字符串的长度。它将字符串作为参数，并返回字符串的长度。

**语法:**

```sql
Len(string/varname)

```

**例 1 :**

```sql
SELECT Len("GEEKSFORGEEKS") AS LengthOfString;

```

**输出–**

| **字符串长度** |
| Thirteen |

**示例-2 :**

```sql
SELECT Len("GFG") AS LengthOfString;

```

**输出–**

| **字符串长度** |
| three |