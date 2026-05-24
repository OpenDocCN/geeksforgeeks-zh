# 马里亚数据库中的 LOCALTIME()和 LAST_DAY()函数

> 原文:[https://www . geesforgeks . org/local time-and-last _ day-function-in-mariadb/](https://www.geeksforgeeks.org/localtime-and-last_day-function-in-mariadb/)

**1。LOCALTIME()函数:**
在马里亚数据库中，LOCALTIME()函数用于返回当前日期和时间。在这个函数中，不会传递任何参数。在字符串上下文中，该函数将以“YYYY-MM-DD HH:MM: SS”格式返回当前日期。在数字上下文中，该函数将以数字格式返回当前日期。

**语法:**

```sql
LOCALTIME( )
```

**参数:**该函数不传递参数。
**返回:**返回当前日期和时间。

**示例-1 :** 它将返回当前日期和时间，并以字符串格式返回。

```sql
SELECT LOCALTIME();
```

**输出:**

```sql
'2020-10-25 08:51:16'
```

**示例-2 :** 它将在当前日期时间的左侧添加 1 个单位，并以数字格式返回。

```sql
SELECT LOCALTIME() + 1;
```

**输出:**

```sql
20201025085117
```

**示例-3 :** 它将在当前日期时间左侧减去 6 个单位，并以数字格式返回。

```sql
SELECT LOCALTIME() - 6;
```

**输出:**

```sql
20201025085110
```

**2。LAST_DAY()函数:**
在马里亚数据库中，LAST_DAY()函数返回给定日期当月的最后一天。在这个函数中，第一个参数将是 date_value。该函数将返回给定日期的最后一天。如果传递的参数日期值不是有效的日期或日期时间值，LAST_DAY 函数将返回空值。

**语法:**

```sql
LAST_DAY(date_value)
```

**参数:**

*   **Date _ value–**从中提取一个月的最后一天的日期或日期时间值。

**返回:**给定日期的最后一天。

**示例-1 :**

```sql
SELECT LAST_DAY('2010-05-20');
```

**输出:**

```sql
'2010-05-31'
```

**示例-2 :**

```sql
SELECT LAST_DAY('2016-03-02 11:24:05');
```

**输出:**

```sql
'2016-03-30'
```

**示例-3 :**

```sql
SELECT LAST_DAY('2020-02-17');
```

**输出:**

```sql
'2020-02-29'
```

**示例-4 :**

```sql
SELECT LAST_DAY('date is: 2020-08-20');
```

**输出:**

```sql
NULL
```

**例-5 :** 返回当月最后一天。今天是 2020 年 10 月 28 日。

```sql
SELECT LAST_DAY(CURDATE());
```

**输出:**

```sql
'2020-10-31'
```

**示例-6 :**

```sql
SELECT LAST_DAY('2019-02-11');
```

**输出:**

```sql
'2019-02-28'
```