# MySQL 中的 PERIOD_ADD()函数

> 原文:[https://www.geeksforgeeks.org/period_add-function-in-mysql/](https://www.geeksforgeeks.org/period_add-function-in-mysql/)

MySQL 中的 PERIOD_ADD()函数有助于给定期间添加特定的月数。PERIOD_ADD()函数将以“**yyymm**格式返回结果值。

**语法:**

```sql
PERIOD_ADD(period, number)

```

**参数:**

*   **周期–**
    周期应为 YYMM 或 YYYYMM 格式。
*   **数字–**
    将被添加到给定期间的月数，该值可以是负数或正数。

**结果:**
该函数将在给定周期中增加特定的月数后返回结果值。

**示例-1 :**
使用 PERIOD_ADD()函数向给定期间添加月份。

```sql
SELECT PERIOD_ADD(202011, 9) As New_period;

```

**输出:**

| 新 _ 期间 |
| Two hundred and two thousand one hundred and eight |

**示例-2 :**
使用 PERIOD_ADD()函数从给定期间减去月份。

```sql
SELECT PERIOD_ADD(202102, -5) As New_period;

```

**输出:**

| 新 _ 期间 |
| Two hundred and two thousand and nine |

**示例-3 :**
从两位数的年期间中加减月份。

```sql
SELECT  
PERIOD_ADD(2109, -5) As New_period1,
PERIOD_ADD(2109, +5) As New_period2;

```

**输出:**

| 新 _ 周期 1 | 新 _ 周期 2 |
| Two hundred and two thousand one hundred and four | Two hundred and two thousand two hundred and two |

**示例-4 :**
使用当前日期和提取功能。

```sql
SELECT  
   CURDATE( ) AS 'Curr_date',
   EXTRACT(YEAR_MONTH FROM CURDATE( )) AS 'Curr_period',
   PERIOD_ADD(EXTRACT(YEAR_MONTH FROM CURDATE( )), 11) AS 'New_period';

```

**输出:**

| 当前日期 | 当前期间 | 新 _ 期间 |
| 2020-11-30 | Two hundred and two thousand and eleven | Two hundred and two thousand one hundred and ten |