# MS 接入中的 InStr()和 InstrRev()功能

> 原文:[https://www . geesforgeks . org/instr-and-instrrev-function-in-ms-access/](https://www.geeksforgeeks.org/instr-and-instrrev-function-in-ms-access/)

**1。函数的作用是:返回一个字符串在另一个字符串中的位置。它总是返回字符串的第一个匹配项。它不区分大小写。如果在 string1 中找不到 string2，或者 string1 为 null，或者函数中的 start 参数大于 string1 的长度，则返回 0；如果 string1 为 null，则返回 null；如果 string2 的长度为零，则返回 start 参数的值。**

**语法–**

```sql
InStr(start, string1, string2, compare)
```

**参数–**

*   开始:可选(默认位置为 1)
*   字符串 1:必选(要搜索的字符串)
*   字符串 2:必选(要搜索的字符串)
*   比较:可选(字符串比较类型)

**可能值–**

*   -1:使用选项比较的设置。
*   0:二进制比较。
*   1:文本比较。
*   2:根据数据库中的信息进行比较。

**返回–**返回 0、1 或空。

**示例–**

```sql
SELECT InStr("geeksforgeeks", "f") 
AS MatchPosition;
```

**输出–**

| 观察位置 |
| six |

**示例–**

```sql
SELECT InStr("DSA self paced", "a") 
AS MatchPosition;
```

**输出–**

| 观察位置 |
| three |

**2。InstrRev()函数:**
InstrRev()函数的工作方式类似于 Instr()函数，但它返回一个字符串在另一个字符串中第一次出现的位置，从字符串的末尾开始。该默认值中的起始参数为-1。

**语法:**

```sql
InstrRev(string1, string2, start, compare)
```

**示例–**

```sql
SELECT InStrRev("geeksforgeeks", "k") 
AS MatchPosition;
```

**输出–**

| 观察位置 |
| Twelve |

**示例–**

```sql
SELECT InStrRev("gfg", "k") 
AS MatchPosition;
```

**输出–**

| 观察位置 |
| Zero |