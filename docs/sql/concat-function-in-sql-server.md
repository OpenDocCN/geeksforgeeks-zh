# SQL Server 中的 CONCAT()函数

> 原文:[https://www . geesforgeks . org/concat-function-in-SQL-server/](https://www.geeksforgeeks.org/concat-function-in-sql-server/)

**CONCAT():**
SQL Server 中的这个函数有助于将两个或多个字符串连接在一起。CONCAT()函数可以接受最少 2 个参数，最多 254 个参数。

**语法:**

```sql
CONCAT(string_1, string_2, .......string_n)
```

**参数:**

*   **string_1，string_2，…。字符串 _ n–**
    需要连接的给定字符串。

**返回:**
该函数连接所有给定的字符串，并将它们作为一个完整的字符串返回。

**适用于以下版本:**

*   SQL Server 2017
*   SQL Server 2016
*   SQL Server 2014
*   SQL Server 2012

**示例-1 :**
一般工作的CONCAT()函数。

*   **Concatenating 3 strings together with space in between –**

    ```sql
    SELECT CONCAT('PYTHON', ' ', 'is', ' ', 'fun!!!') 
    As Combined;
    ```

    **输出:**

    | 联合的；共同的 |
    | PYTHON 很好玩！！！ |

*   **Concatenating more than 3 strings together –**

    ```sql
    SELECT CONCAT
    ('Every', 'next', 'level', 'of', 'your', 'life', 'demands', 'a', 'new', 'you!') 
    As Combined;
    ```

    **输出:**

    | 联合的；共同的 |
    | everynext level yourselftedemandsanewyou！ |

**示例-2 :**
使用带有 CONCAT()函数的变量，我们将字符串分配给变量，然后连接它们。

```sql
DECLARE @Str1 AS VARCHAR(100)='Think'
DECLARE @Str2 AS VARCHAR(100)='-'
DECLARE @Str3 AS VARCHAR(100)='green'
DECLARE @Str4 AS VARCHAR(100)=' '
DECLARE @Str5 AS VARCHAR(100)='Be'
DECLARE @Str6 AS VARCHAR(100)='-'
DECLARE @Str7 AS VARCHAR(100)='green'

SELECT CONCAT(@Str1, @Str2, @Str3, @str4, @str5, @str6, @str7) AS Combined;
```

**输出:**

| 联合的；共同的 |
| 绿色思维 |

**示例-3 :**
使用 CONCAT()函数连接数值表达式，这里我们组合数值来代替字符串。

```sql
SELECT CONCAT(13, 03, 1999) 
AS Combined;
```

**输出:**

| 联合的；共同的 |
| One million three hundred and thirty-one thousand nine hundred and ninety-nine |