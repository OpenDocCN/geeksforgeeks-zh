# MySQL 中的 DAYOFMONTH()函数

> 原文:[https://www.geeksforgeeks.org/dayofmonth-function-in-mysql/](https://www.geeksforgeeks.org/dayofmonth-function-in-mysql/)

**DAYOFMONTH()函数:**
这个函数在 MySQL 中用来返回指定日期(从 1 到 31 的数字)的月份中的某一天。这个函数等于 DAY()函数。

**语法:**

```sql
DAYOFMONTH(date)

```

**参数:**
该方法接受如下所示的参数。

*   **日期–**提取日期的指定日期。

**返回:**
返回指定日期(1 到 31 之间的数字)的月份。

**示例-1 :**
从指定日期“2020-11-24”获取当月的某一天。

```sql
SELECT DAYOFMONTH("2020-11-24");  

```

**输出:**

```sql
24

```

**示例-2 :**
从指定日期“2020-11-22 07:12:23”获取当月的某一天。

```sql
SELECT DAYOFMONTH("2020-11-22 07:12:23");  

```

**输出:**

```sql
22

```

**示例-3 :**
获取当前系统日期的月份。

```sql
SELECT DAYOFMONTH(CURDATE());

```

**输出:**

```sql
24

```

**应用:**
该函数用于返回指定日期(1 到 31 之间的数字)的月份。