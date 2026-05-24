# SQL Server 中的 SPACE()函数

> 原文:[https://www.geeksforgeeks.org/space-function-in-sql-server/](https://www.geeksforgeeks.org/space-function-in-sql-server/)

**SPACE():**
SQL Server 中的这个函数有助于返回一个有指定空格数的字符串。这个功能在同名的 MYSQL 中也有。

**语法:**

```sql
SPACE(number)
```

**参数:**
该函数只接受一个参数。

*   **number–**
    它将空格数降级。

**返回:**

*   如果数字是正数，函数将返回一个具有指定空格数的字符串。
*   如果数字为负，函数将返回空值。

**适用于以下版本:**

*   SQL Server 2017
*   SQL Server 2016
*   SQL Server 2014
*   SQL Server 2012
*   2008
*   SQL Server 2008
*   SQL Server 2005

**示例-1:**
SPACE()函数的基本工作原理，该函数将返回 5 个空格。

```sql
SELECT SPACE(5) 
AS Result;
```

**输出:**
该函数将返回 5 个空格。

| 结果 |
| ' ' |

**示例-2 :**
使用 SPACE()函数连接 2 个或更多字符串。

*   Concatenating 2 strings using the SPACE() function, we take 2 strings and assign specific spaces in between.

    ```sql
    SELECT 'HI!' + SPACE(6) + 'NiceToSeeYou' 
    AS Result;
    ```

    **输出:**

    | 结果 |
    | 你好！尼克西你 |

*   Concatenating 3 strings using SPACE() function, we take 2 strings and assign specific spaces among them.

    ```sql
    SELECT 'GEEKS' + SPACE(5) + 'FOR'+ SPACE(5) +'GEEKS' AS Result;
    ```

    **输出:**

    | 结果 |
    | 极客的极客 |

**示例-3 :**
如果用户输入负数作为参数，那么函数将返回 NULL。

```sql
SELECT SPACE(-20) 
AS Result;
```

**输出:**

| 结果 |
| 空 |

**示例-4 :**
使用变量处理 SPACE()函数，我们将变量与 SPACE()函数一起使用。

```sql
DECLARE @space_Size int
SET @space_Size = 7
SELECT 'KeepChasing' + SPACE(@space_size) + 'YourDreams' 
AS Result;
```

**输出:**

| 结果 |
| 继续追 |