# SQL Server 中的 SUBSTRING()函数

> 原文:[https://www . geesforgeks . org/substring-function-in-SQL-server/](https://www.geeksforgeeks.org/substring-function-in-sql-server/)

SUBSTRING()函数从输入字符串中给定长度的位置开始提取子字符串。在子字符串的情况下，您需要一个输入字符串，并且需要提到字符串的起点和总长度。

```sql
Input  : String, start, length
output : substring.

```

**语法:**

```sql
SUBSTRING(input_string, start, length);

```

**参数:**
SUBSTRING 函数接受 STRING、start、length 三个参数。让我们看看。

*   **input _ string–**可以是字符、二进制、文本、ntext 或图像表达式。
*   **start–**它是一个整数，定义返回的子字符串开始的位置。字符串中的第一个位置是 1。
*   **长度–**它是一个正整数，指定要从子字符串返回的字符数。

**返回:**
从输入字符串的某个位置开始，返回指定长度的子字符串。

**示例-1 :**
使用带有文字字符串的 SUBSTRING()函数。

```sql
SELECT SUBSTRING('SQL In Geeksforgeeks', 7, 18 ) 
AS ExtractString;

```

**输出:**

| 提取字符串 |
| 极客们 |

**示例-2 :**
使用 SUBSTRING()函数处理表列。

**牌桌-玩家 _ 详情**

| **PlayerId** | **玩家姓名** | **城市** |
| Forty-five | 罗希特·夏尔马 | 孟买 |
| Eighteen | 维拉·科尔 | 班加罗尔 |
| seven | 迪奥尼女士 | 金奈 |
| Thirty-three | 哈迪克·潘迪亚 | 孟买 |
| forty-two | 锡卡扎万 | 德里 |

```sql
SELECT SUBSTRING(PlayerName, 1, 5) AS ExtractString
FROM Player_Details;

```

**输出:**

| 提取字符串 |
| rohit！rohit |
| 维拉特 |
| MS Dh |
| 哈尔迪 |
| 锡卡 |