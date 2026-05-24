# MySQL 中的 SUBDATE()函数

> 原文:[https://www.geeksforgeeks.org/subdate-function-in-mysql/](https://www.geeksforgeeks.org/subdate-function-in-mysql/)

**SUBDATE**()MySQL 中的函数用于从给定日期中减去一个时间值(作为间隔)。

**语法:**

```sql
SUBDATE(date, INTERVAL expr unit)

```

**参数:**该函数接受如下三个参数:

**日期**:首次指定日期。

**表达式:**要减去的时间/日期间隔的值。

**单位:**区间的类型。它可以是以下值之一:

*   微秒
*   第二
*   分钟
*   小时
*   天
*   周
*   月
*   四分之一
*   年
*   秒 _ 微秒
*   MINUTE _ 微秒
*   分钟 _ 秒
*   小时 _ 微秒
*   小时 _ 秒
*   小时 _ 分钟
*   DAY _ 微秒
*   第二天
*   日 _ 分钟
*   日 _ 小时
*   年 _ 月

**返回:**
减去时间/日期间隔后返回日期。

**示例-1 :**
从日期中减去一个间隔值，并返回日期，其中日期以 YYYY-MM-DD 格式指定，间隔以天为单位:

```sql
SELECT SUBDATE("2020-11-25", INTERVAL 30 DAY) 
AS RESULTANTDATE;

```

**输出:**

| 结果日期 |
| --- |
| 2020-10-26 |

**示例-2 :**
从日期中减去一个间隔值，并返回以 YYYY-MM-DD 格式指定日期的日期和以负月份为单位的间隔:

```sql
SELECT SUBDATE("2020-11-25", INTERVAL -02 MONTH) 
AS RESULTANTDATE;

```

**输出:**

| 结果日期 |
| --- |
| 2021-01-25 |

**示例-3 :**
从日期中减去一个间隔值，并返回日期，其中日期以 YYYY-MM-DD 格式指定，间隔以小时为单位。

```sql
SELECT SUBDATE("2020-11-25 04:12:06",  INTERVAL 09 HOUR) 
AS RESULTANTDATE;

```

**输出:**

| 结果日期 |
| --- |
| 2020-11-24 19:12:06 |

**示例-4 :**
从日期中减去一个间隔值，并返回日期，其中日期以 YYYY-MM-DD 和 Interval in QUARTER 的格式指定。

```sql
SELECT SUBDATE("2020-11-25 04:12:06",  INTERVAL 09 QUARTER) 
AS RESULTANTDATE;

```

**输出:**

| 结果日期 |
| --- |
| 2018-08-25 04:12:06 |

**例 5 :**
从日期中减去一个区间值，返回以 YYYY-MM-DD 和 Interval in -YEAR 格式指定日期的日期。

```sql
SELECT SUBDATE("2020-11-25 12:19:36",  INTERVAL -01 YEAR) 
AS RESULTANTDATE;

```

**输出:**

| 结果日期 |
| --- |
| 2021-11-25 12:19:36 |