# SQL Server 中的 CHAR()函数

> 原文:[https://www.geeksforgeeks.org/char-function-in-sql-server/](https://www.geeksforgeeks.org/char-function-in-sql-server/)

**CHAR() :**
这个函数有助于将一个 int ASCII 码转换为字符值，即如果用户传递一个整数作为参数，CHAR()函数会解释整数值并返回其对应的字符值。

**语法:**

```sql
CHAR(integer_value)
```

**参数:**
这个函数只接受一个参数。

*   **整数值–**
    0 到 255 之间的任意整数值。

**返回:**

*   该函数将返回对应于给定整数代码的字符值。
*   如果整数值超过给定范围，函数将返回空值。

**适用于以下版本:**

*   SQL Server 2017
*   SQL Server 2016
*   SQL Server 2014
*   SQL Server 2012
*   2008
*   SQL Server 2008
*   SQL Server 2005

**例-1:**
CHAR()函数的基本用法，函数会返回‘P’和‘D’。

```sql
SELECT  
CHAR(80) AS 'Character1',
CHAR(100) AS 'Character2';
```

**输出:**

| 特性 | 特性 |
| P | d |

**示例-2 :**
如果 CHAR()函数超出整数值的范围，则该函数将返回 NULL。

```sql
SELECT CHAR(260) 
AS 'Outcome';
```

**输出:**

| 结果 |
| 空 |

**示例-3 :**
如何控制 CHAR()函数中的字符，我们在它们之间使用字符串和 CHAR()函数，

```sql
SELECT 'Vansh' + CHAR(13) + 'vgaur12345@gmail.com' 
AS 'Name_Email';
```

**输出:**

| 姓名 _ 电子邮件 |
| 万什vgaur 12345@gmail . com |

**示例-4 :**
如果用户在 CHAR()函数中传递两个参数，函数将返回一个错误。

```sql
SELECT CHAR(91, 200) 
AS 'Outcome';
```

**输出:**

```sql
The char function requires 1 argument(s)
```