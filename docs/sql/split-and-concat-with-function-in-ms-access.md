# 在移动台接入

中使用&功能分割()和连接

> 原文:[https://www . geesforgeks . org/split-and-concat-with-function-in-ms-access/](https://www.geeksforgeeks.org/split-and-concat-with-function-in-ms-access/)

**1。Split()函数:**
在 MS Access 中，Split()函数将字符串拆分为字符串数组。在这个函数中，我们将传递字符串和分隔符，函数将通过它们来分隔字符串。如果我们不传递分隔符，那么它将根据空格分隔字符串。

**语法:**

```sql
Split(expression, delimiter, limit, compare)
```

**参数:**

*   **表达式–**根据分隔符拆分为子字符串的字符串。
*   **分隔符–**可选。用于将表达式拆分为子字符串的分隔符。
*   **极限–**可选。从表达式中拆分的最大子字符串数。
*   **比较–**可选。对于二进制比较值将通过 0，对于文本比较值将通过 1。

**返回:**返回带分隔符的字符串。

**示例-1 :**

```sql
SELECT Split("Geeks For Geeks") AS SplitString;
```

**输出:**

| SplitString |
| {“极客”，“为”，“极客”} |

**示例-2 :**

```sql
SELECT Split("geeks:for:geeks", ":") AS SplitString;
```

**输出:**

| SplitString |
| {“极客”，“为”，“极客”} |

**示例-3 :**

```sql
SELECT Split("The best computer science portal")
```

**输出:**

```sql
{"The", "best", "computer", "science", "portal"}
```

**2。在 MS Access 中，我们可以借助&将两个或两个以上的字符串组合成一个字符串。它会将所有字符串组合成一个字符串。我们可以使用&运算符将多个字符串串联成一个字符串。在 Concat 函数的帮助下，字符串之间也可以进行连接。&运算符没有参数或自变量。**

**语法:**

```sql
string1 & string2 & string3 &string_n
```

**示例-1 :**

```sql
SELECT "GEEKS" & "FOR" & "GEEKS" AS The_String;
```

**输出:**

| 字符串 |
| GEEKSFORGEEKS |

**示例-2 :**

```sql
SELECT "A" & NULL & "B"& NULL & "C";
```

**输出:**

```sql
"ABC"
```

**示例-3 :**

```sql
SELECT "COMPUTER" & " " & "SCIENCE"  AS The_String;
```

**输出:**

| 字符串 |
| 计算机科学 |