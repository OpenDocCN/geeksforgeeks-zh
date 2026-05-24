# 马里亚数据库中的 DATE()和 DATE_ADD()函数

> 原文:[https://www . geesforgeks . org/date-and-date _ add-function-in-Maria db/](https://www.geeksforgeeks.org/date-and-date_add-function-in-mariadb/)

**1。日期()功能:**

在 MariaDB 中，DATE()函数用于返回从日期或日期时间表达式中提取的日期值。在此函数中，第一个参数将是日期或日期时间。该函数将返回从表达式中提取的日期值。如果表达式不是日期或日期时间，则此函数将返回空值。

**语法:**

```sql
DATE(expression)
```

**参数:**

*   **表达式–**日期或日期时间值。

**返回:**日期时间中的日期值。

**示例-1 :**

```sql
SELECT DATE('2020-09-11 11:13:19');
```

**输出:**

```sql
'2020-09-11'
```

**示例-2 :**

```sql
SELECT DATE('2020-04-12 11:13:01.000001');
```

**输出:**

```sql
'2020-04-12'
```

**示例-3 :**

```sql
SELECT DATE('Today is 2020-10-17');
```

**输出:**

```sql
NULL
```

**2。DATE_ADD()功能:**

在 MariaDB 中，DATE_ADD()函数用于返回时间/DateTime 值，在该值之后添加了某个日期/时间间隔。在这个函数中，第一个参数是 start_value，第二个参数是 interval 值。该函数将以给定的时间间隔返回日期时间。该函数的工作方式类似于 DATE_SUB 函数。如果给定的间隔是负的。如果间隔值对于单位来说太短，那么 DATE_ADD 函数将假设没有提供间隔值的最左侧部分。

**语法:**

```sql
DATE_ADD(date, INTERVAL value unit)
```

**参数:**

*   **Date–** The date to which the interval should be added.
*   **Days–** The number of days added to the date.
*   **Value–** The time/date interval you want to add.
*   **Unit–** The unit type of interval, such as DAY, MONTH, MINUTE, HOUR, etc.

**返回:**时间/日期时间值，在该值之后添加了某个日期间隔。

**示例-1 :**

```sql
SELECT DATE_ADD('2020-01-10 08:44:21', INTERVAL 25 MINUTE);
```

**输出:**

```sql
'2020-01-10 09:09:21'
```

**示例-2 :**

```sql
SELECT DATE_ADD('2014-05-17 08:44:21.000001', INTERVAL '7 1:03:12.000001' DAY_MICROSECOND);
```

**输出:**

```sql
'2014-05-24 09:47:33.000002'
```

**示例-3 :**

```sql
SELECT DATE_ADD('2019-07-10', INTERVAL '1-2' YEAR_MONTH);
```

**输出:**

```sql
'2020-09-10'
```