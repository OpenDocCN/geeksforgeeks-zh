# MySQL 中的 DAYOFWEEK()函数

> 原文:[https://www.geeksforgeeks.org/dayofweek-function-in-mysql/](https://www.geeksforgeeks.org/dayofweek-function-in-mysql/)

**DAYOFWEEK()函数:**
这个函数在 [MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中用来返回指定日期(1 到 7 之间的数字)的工作日索引。

**注:**1 =周日，2 =周一，3 =周二，4 =周三，5 =周四，6 =周五，7 =周六。

**语法:**

```sql
DAYOFWEEK(date)

```

**参数:**
该方法接受一个参数，如下图所示:

*   **日期–**返回工作日索引的指定日期。

**返回:**
返回指定日期的工作日索引(1 到 7 之间的数字)。

**示例-1 :**
获取指定日期“2020-11-24”的工作日索引。

```sql
SELECT DAYOFWEEK("2020-11-24");

```

**输出:**

```sql
3
```

**示例-2 :**
获取指定日期“2020-11-22 07:12:23”的工作日索引。

```sql
SELECT DAYOFWEEK("2020-11-22 07:12:23");

```

**输出:**

```sql
1
```

**示例-3 :**
获取当前系统日期的工作日索引。

```sql
SELECT DAYOFWEEK(CURDATE());

```

**输出:**

```sql
3
```

**应用:**
该函数用于返回指定日期(1 到 7 之间的数字)的工作日指数。