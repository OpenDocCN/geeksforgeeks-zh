# MS 接入中的 StrConv()和 StrReverse()功能

> 原文:[https://www . geesforgeks . org/strconv-and-strreverse-function in-ms-access/](https://www.geeksforgeeks.org/strconv-and-strreverse-function-in-ms-access/)

**1。函数的作用是:**
在 MS Access 中，函数返回一个转换后的字符串。在这里，我们将传递第一个参数字符串和第二个参数转换。

<center>

| 可能的转换值 |
| --- |
| one | 对于大写字母 |
| Two | 对于小写字母 |
| three | 每个单词的第一个字母要大写 |
| four | 对于窄字符到宽字符 |
| Sixteen | 将平假名转换为片假名(仅限日本) |
| Thirty-two | 将片假名转换为平假名(仅限日本) |
| Sixty-four | 对于转换为 unicode |
| One hundred and twenty-eight | 对于 Unicode 到默认页面代码 |

</center>

**语法:**

```sql
StrConv(string1, conversion)

```

**示例-1 :**

```sql
SELECT StrConv("GeeksforGeeks", 1) AS ConvertedString;

```

**输出–**

| **转换字符串** |
| GEEKSFORGEEKS |

**示例-2 :**

```sql
SELECT StrConv("geeks for geeks", 3) AS ConvertedString;

```

**输出–**

| **转换字符串** |
| 极客为极客 |

**2。函数的作用是:**
在 MS Access 中，函数的作用是:反转给定的字符串。在这个函数中，一个字符串将被传递，它将返回反转的字符串。

**语法:**

```sql
StrReverse(string)

```

**示例-1 :**

```sql
SELECT StrReverse("Geeksforgeeks") AS StringReverse;

```

**输出–**

| **挤压反转** |
| 斯基格罗夫斯基格 |

**示例-2 :**

```sql
SELECT StrReverse("Gfg") AS StringReverse;

```

**输出–**

| **挤压反转** |
| gfG |