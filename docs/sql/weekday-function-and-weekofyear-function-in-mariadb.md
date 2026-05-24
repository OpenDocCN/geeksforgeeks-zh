# 马里亚数据库中的 WEEKDAY 函数和 WEEKOFYEAR 函数

> 原文:[https://www . geesforgeks . org/weekday-function-and-weekof year-function-in-mariadb/](https://www.geeksforgeeks.org/weekday-function-and-weekofyear-function-in-mariadb/)

**1。Weekday 函数:**
在马里亚数据库中，WEEKDAY 函数返回日期的工作日索引。在这个函数中，第一个参数将是日期值。此函数返回日期的工作日索引。In WEEKDAY 函数返回给定日期值的工作日的索引值。它的工作原理与 DAYNAME 函数相反。和索引值如下。

```sql
0=Monday, 
1=Tuesday, 
2=Wednesday, 
3=Thursday, 
4=Friday, 
5=Saturday, 
6=Sunday 
```

**语法:**

```sql
WEEKDAY( date_value )

```

**参数:**

*   **日期值–**从中提取工作日索引的日期或日期时间值。

**返回:**
它将返回日期时间表达式的时间部分。

**示例-1 :**

```sql
SELECT WEEKDAY('2014-05-20');

```

**输出:**

```sql
1

```

**示例-2 :**
函数返回当前系统日期。今天是星期五，所以它将返回 5 点。

```sql
SELECT WEEKDAY(CURDATE()); 
```

**输出:**

```sql
5

```

**2。WEEKOFYEAR 函数:**
在马里亚数据库中，WEEKOFYEAR 函数用于返回日期值的一年中的星期。在这个函数中，第一个参数将是日期值。该函数返回给定日期值的一年中的星期(1 到 53 之间的数字)。此函数假设一周的第一天是星期一，并且第一周有 3 天以上。WEEKOFYEAR 函数返回的结果与 WEEK 函数相同，语法为 WEEK(date_value，3)。

**语法:**

```sql
WEEKOFYEAR( date_value )

```

**参数:**

*   **日期值–**从中提取一年中某一周的日期或日期时间值。

**Return :**
返回一年中某一周的日期值。

**示例-1 :**

```sql
SELECT WEEKOFYEAR('2020-01-01');

```

**输出:**

```sql
1

```