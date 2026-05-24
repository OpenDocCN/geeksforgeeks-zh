# 马里亚数据库中的 MINUTE()和 MONTH()

> 原文:[https://www.geeksforgeeks.org/minute-and-month-in-mariadb/](https://www.geeksforgeeks.org/minute-and-month-in-mariadb/)

**1。分钟()功能:**

在马里亚数据库中，分钟函数用于返回日期值的分钟部分。在这个函数中，第一个参数是日期。分钟函数将返回 0 到 59 之间的分钟，并给出一个日期值。我们将传递一个日期/日期时间，它将返回其中的分钟部分。

**语法:**

```sql
MINUTE( date_value )

```

```sql
Minute range = [ 0 to 59 ]
```

**参数:**

<figure class="table">

| **参数** | **描述** |
| --- | --- |
| 日期 _ 值 | 从中提取分钟的时间或日期时间值。 |

</figure>

**返回:**

日期值的分钟部分。

**示例-1 :**

```sql
SELECT MINUTE('2019-05-19 09:21:18.000004');

```

**输出:**

```sql
19

```

**示例-2 :**

```sql
SELECT MINUTE('838:59:01');

```

**输出:**

```sql
59

```

**示例-3 :**

curtime()函数返回当前时间。现在时间是 07:27:24。

```sql
SELECT MINUTE(CURTIME());

```

**输出:**

```sql
27

```

**2。MONTH()功能:**

在马里亚数据库中，月函数用于返回日期值的月份部分。在这个函数中，第一个参数是 date_value。在日期格式中，它是日期的一部分，它将返回从 1 到 12 或 1 月到 12 月等月份值。取决于不同的日期格式。该函数返回给定日期值的月份(从 1 到 12 的数字)。

**语法:**

```sql
 MONTH( date_value )

```

```sql
Month range (In number) = [1 to 12]
```

**参数:**

<figure class="table">

| **parameter** | **Describe** |
| --- | --- |
| Date _ value | from which to extract the time of month or date time value. |

</figure>

**返回:**

从日期开始的月份部分。

**示例-1 :**

```sql
SELECT MONTH('2017-06-19 09:04:10');

```

**输出:**

```sql
6

```

**示例-2 :**

```sql
SELECT MINUTE('838:59:01');

```

**输出:**

```sql
59

```

**示例-3 :**

curtime()函数返回系统的当前时间。今天是 2020 年 07 月 11 日

```sql
SELECT MINUTE(CURTIME());

```

**输出:**

```sql
11

```