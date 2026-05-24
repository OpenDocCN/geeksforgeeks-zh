# 在 MariaDB 中提取()和 DAYOFYEAR()函数

> 原文:[https://www . geeksforgeeks . org/extract-and-dayofyear-function-in-mariadb/](https://www.geeksforgeeks.org/extract-and-dayofyear-function-in-mariadb/)

**1。提取()功能:**

在 MariaDB 中，EXTRATE()函数用于返回从日期中提取的提取部分。在这个函数中，第一个参数将是一个表达式。表达式的第一部分是单位，第二部分是日期。该函数将返回从日期中提取的单位部分。

**语法:**

```sql
EXTRACT(unit FROM date)
```

**参数:**

*   **单位–**间隔的单位类型，如日、月、分、小时等。
*   **日期–**从中提取日期部分的日期或日期时间值。

**返回:**某一日期的单位零件。

**示例-1 :**

```sql
SELECT EXTRACT(SECOND FROM '2020-05-19 08:44:21');
```

**输出:**

```sql
21
```

**示例-2 :**

```sql
SELECT EXTRACT(YEAR_MONTH FROM '2010-05-19');
```

**输出:**

```sql
201005
```

**示例-3 :**

```sql
SELECT EXTRACT(MINUTE_MICROSECOND FROM '2014-05-19 08:44:21.000001');
```

**输出:**

```sql
4421000001
```

**2。DAYOFYEAR()功能:**

在 MariaDB 中，DAYOFYEAR()函数用于返回日期值的一年中的某一天。在这个函数中，第一个参数将是 date_value。该函数将从作为参数传递的日期开始返回一年中的第 y 天。该函数返回给定日期值的一年中的某一天(1 到 366 之间的数字)。

**语法:**

```sql
DAYOFYEAR(date_value)
```

**参数:**

*   **Date–** Select the date of a certain day part of the year.

**返回:**过去日期的一年中的某一天。

**示例-1 :**

```sql
SELECT DAYOFYEAR('2015-12-31');
```

**输出:**

```sql
365
```

**示例-2 :**

```sql
SELECT DAYOFYEAR('2018-05-20')
```

**输出:**

```sql
140
```

**示例-3 :**

```sql
SELECT DAYOFYEAR('2020-01-02')
```

**输出:**

```sql
2
```