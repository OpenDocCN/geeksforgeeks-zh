# SQL Server 中的 DIFFERENCE()函数

> 原文:[https://www . geesforgeks . org/difference-function-in-SQL-server/](https://www.geeksforgeeks.org/difference-function-in-sql-server/)

**DIFFERENCE()** 函数比较两个不同的 SOUNDEX 值，并返回整数的值。该值衡量 SOUNDEX 值的匹配程度，范围从 0 到 4。值 0 表示 SOUNDEX 值之间的相似性较弱或没有相似性；4 表示 SOUNDEX 值极其相似，甚至完全相同。

**语法:**

```sql
DIFFERENCE(string, string)
```

**参数:**该方法接受两个参数，如上所述，描述如下–

*   **字符串，string–**
    它是字符数据的字母数字表达。它可以是常量、变量或列。

**返回:**返回一个整数值，测量两个不同字符串的 SOUNDEX()值之差。

**示例-1 :**
使用具有相似 SOUNDEX()值的 DIFFERENCE()函数。

```sql
SELECT SOUNDEX('poor') soundex_poor, SOUNDEX('pour') soundex_pour, 
DIFFERENCE('poor', 'pour') similarity;
```

**输出:**

| soundex_poor | soundex _ 用于 | 类似 |
| P600 | P600 | four |

**示例-2 :**
返回差值 3，差值越小越好。

```sql
SELECT SOUNDEX('GeeksForGeeks'), SOUNDEX('GeeksOfGeeks'),
DIFFERENCE('GeeksForGeeks', 'GeeksOfGeeks');
```

**输出:**

```sql
3
```

**示例-3 :**
返回一个差值 2，中间可能的差值。

```sql
SELECT SOUNDEX('GeeksForGeeks') soundex_GeeksForGeeks, SOUNDEX('GFG') soundex_GFG,
DIFFERENCE('GeeksForGeeks', 'GFG') similarity;
```

**输出:**

| soundex_GeeksForGeeks(声音 x _ geeksforgeeks) | soundex_GFG 音效档 | 类似 |
| G216 | G120 | Two |

**示例-4 :**
返回最大可能差值 0 的差值。

```sql
SELECT SOUNDEX('javascript') soundex_javascript, SOUNDEX('c#') soundex_c#,
DIFFERENCE('javascript', 'c#') similarity;
```

**输出:**

| soundex_javascript | soundex_c# | 类似 |
| J126 | C000 | Zero |