# SQL Server 中的 UNICODE()函数

> 原文:[https://www . geesforgeks . org/unicode-function-in-SQL-server/](https://www.geeksforgeeks.org/unicode-function-in-sql-server/)

在本文中，我们将介绍 Unicode()函数，您将看到给定特定字符或表达式字符的 UNICODE。

**UNICODE() :**
是获取输入表达式第一个字符整数值的函数，由 UNICODE 标准定义。

**语法:**

```sql
UNICODE(ncharacter_expression)

```

**参数:**
UNICODE 函数接受单个参数，这意味着如果您只给出一个字符，或者您可以给出表达式作为输入，那么它将读取第一个字符，并为相同的字符返回 UNICODE。

**ncharacter _ expression:**
是 nchar 或 nvarchar 的表达。

**返回–**
UNICODE 函数将为第一个字符提供一个整数值。它为输入表达式的第一个字符返回一个整数值或 Unicode 值。

**示例-1 :**
它将返回输入表达式第一个字符的整数值。

```sql
SELECT UNICODE('MS Dhoni');

```

**输出:**

```sql
77

```

**示例-2 :**
对表列使用 UNICODE 函数。

**牌桌-玩家 _ 详情**

| 球员 | 玩家名称 | 城市 |
| Forty-five | 罗希特·夏尔马 | 孟买 |
| Eighteen | 维拉·科尔 | 班加罗尔 |
| seven | 迪奥尼女士 | 金奈 |
| forty-two | 锡卡扎万 | 德里 |

```sql
SELECT UNICODE(PlayerName) AS UnicodeOfFirstChar, PlayerName 
FROM Player_Details;

```

**输出:**

| UnicodeOfFirstChar | 玩家名称 |
| Eighty-two | 罗希特·夏尔马 |
| Eighty-six | 维拉·科尔 |
| Seventy-seven | 迪奥尼女士 |
| Eighty-three | 锡卡扎万 |