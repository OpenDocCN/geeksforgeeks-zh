# 现在()和 MonthName()在马里亚数据库

> 原文:[https://www.geeksforgeeks.org/now-and-monthname-in-mariadb/](https://www.geeksforgeeks.org/now-and-monthname-in-mariadb/)

**1。Now()功能:**

在马里亚数据库中，现在函数用来返回当前的日期和时间。在这个函数中，不会传递任何参数。对于字符串上下文，当前日期为“YYYYMMDDHHMMSS”格式，对于数字上下文，当前日期为 YYYYMMDDHHMMSS 格式，该函数将返回。它的工作方式类似于 CURRENT_TIMESTAMP、LOCALTIME 和 LOCALTIMESTAMP 函数。

**语法:**

```sql
NOW()

```

**参数:**

| **参数** | **说明** |
| --- | --- |
| 无 | 此功能不传递参数 |

**返回:**

返回当前日期和时间。

**示例-1 :**

```sql
SELECT NOW();

```

**输出:**

```sql
'2020-11-07 07:59:41'

```

**示例-2 :**

```sql
SELECT NOW() + 10;

```

**输出:**

```sql
20201107075951

```

**示例-3 :**

```sql
SELECT NOW() -15;

```

**输出:**

```sql
20201107075926

```

**2。MonthName()函数:**

在马里亚数据库中，MonthName 函数用于返回日期的月份全名。在这个函数中，第一个参数是 date_value。此函数将返回从日期值开始的月份的全名。该函数返回给定日期值的月份全名(一月、二月、…十二月)。

**语法:**

```sql
 MONTHNAME( date_value )

```

**参数:**

| **parameter** | **Describe** |
| --- | --- |
| date _ value | the time or date-time value from which the month name is extracted. |

**返回:**

从日期开始的月份部分的名称。

**示例-1 :**

```sql
SELECT MONTHNAME('2018-03-19 09:22:05.999999')

```

**输出:**

```sql
March

```

**示例-2 :**

```sql
SELECT MONTHNAME('2020-06-01');

```

**输出:**

```sql
June

```

**示例-3 :**

curtime()函数返回系统的当前时间。今天是 2020 年 07 月 11 日，当月是 11 月

```sql
SELECT MONTHNAME(CURTIME());

```

**输出:**

```sql
November

```