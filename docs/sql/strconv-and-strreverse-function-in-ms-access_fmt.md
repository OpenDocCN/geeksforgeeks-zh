# MS Access 中的 StrConv() 和 StrReverse() 函数

> 原文: [https://www.geeksforgeeks.org/strconv-and-strreverse-function-in-ms-access/](https://www.geeksforgeeks.org/strconv-and-strreverse-function-in-ms-access/)

## StrConv() 函数

在 MS Access 中，`StrConv()` 函数返回一个转换后的字符串。在这里，我们将传递第一个参数字符串和第二个参数转换。

| 可能的转换值 |
| --- |
| `1` | 对于大写字母 |
| `2` | 对于小写字母 |
| `3` | 每个单词的第一个字母要大写 |
| `4` | 对于窄字符到宽字符 |
| `6` | 将平假名转换为片假名(仅限日本) |
| `7` | 将片假名转换为平假名(仅限日本) |
| `8` | 对于转换为 unicode |
| `9` | 对于 Unicode 到默认页面代码 |

**语法:**

```sql
StrConv(string1, conversion)
```

**示例-1:**

```sql
SELECT StrConv("GeeksforGeeks", 1) AS ConvertedString;
```

**输出:**

| **转换字符串** |
| --- |
| GEEKSFORGEEKS |

**示例-2:**

```sql
SELECT StrConv("geeks for geeks", 3) AS ConvertedString;
```

**输出:**

| **转换字符串** |
| --- |
| 极客为极客 |

## StrReverse() 函数

在 MS Access 中，`StrReverse()` 函数的作用是反转给定的字符串。在这个函数中，一个字符串将被传递，它将返回反转的字符串。

**语法:**

```sql
StrReverse(string)
```

**示例-1:**

```sql
SELECT StrReverse("Geeksforgeeks") AS StringReverse;
```

**输出:**

| **StringReverse** |
| --- |
| 斯基格罗夫斯基格 |

**示例-2:**

```sql
SELECT StrReverse("Gfg") AS StringReverse;
```

**输出:**

| **StringReverse** |
| --- |
| gfG |