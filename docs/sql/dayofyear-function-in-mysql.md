# MySQL 中的 DAYOFYEAR()函数

> 原文:[https://www.geeksforgeeks.org/dayofyear-function-in-mysql/](https://www.geeksforgeeks.org/dayofyear-function-in-mysql/)

**DAYOFYEAR()函数:**此函数在 [MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中用于返回指定日期(1 到 366 之间的数字)的一年中的某一天。

**语法:**

```sql
DAYOFYEAR(date)
```

**参数:**

该方法接受如下所示的参数:

*   **日期:**返回一年中某一天的指定日期

**返回:**

它返回指定日期的一年中的某一天(1 到 366 之间的数字)。

**示例-1 :**

获取指定日期“2020-11-24”的日期。

```sql
SELECT DAYOFYEAR("2020-06-24");
```

**输出:**

```sql
176
```

**示例-2 :**

获取指定日期“2020-11-22 07:12:23”的日期。

```sql
SELECT DAYOFYEAR("2020-10-22 07:12:23");
```

**输出:**

```sql
296
```

**示例-3 :**

获取当前系统日期的日期。

```sql
SELECT DAYOFYEAR(CURDATE());
```

**输出:**

```sql
329
```