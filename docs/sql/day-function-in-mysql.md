# MySQL 中的 DAY()函数

> 原文:[https://www.geeksforgeeks.org/day-function-in-mysql/](https://www.geeksforgeeks.org/day-function-in-mysql/)

**DAY()函数:**
该函数在 [MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中用于返回指定日期(1 到 31 之间的数字)的月份中的某一天。这个函数等于 DAYOFMONTH()函数。

**语法:**

```sql
DAY(date)

```

**参数:**
该方法接受一个参数，如下图所示:

*   **日期:**提取日期的指定日期。

**返回:**
返回指定日期(1 到 31 之间的数字)的月份。

**示例-1 :**
从指定日期“2020-11-24”获取当月的某一天。

```sql
SELECT DAY("2020-11-24"); 

```

**输出:**

```sql
24
```

**示例-2 :**
从指定日期“2020-11-22 07:12:23”获取当月的某一天。

```sql
SELECT DAY("2020-11-22 07:12:23");

```

**输出:**

```sql
22
```

**示例-3 :**
获取当前系统日期的月份。

```sql
SELECT DAY(CURDATE());

```

**输出:**

```sql
24
```

**应用:**
该函数用于返回指定日期(1 到 31 之间的数字)的月份。