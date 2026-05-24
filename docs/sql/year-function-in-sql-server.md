# SQL Server 中的 YEAR()函数

> 原文:[https://www.geeksforgeeks.org/year-function-in-sql-server/](https://www.geeksforgeeks.org/year-function-in-sql-server/)

**YEAR()函数:**
SQL Server 中的这个函数用于返回指定日期的年份。

**特征:**

*   该函数用于查找指定日期的年份。
*   该功能属于日期功能。
*   该函数只接受一个参数，即日期。
*   该功能还可以包括带有规定日期的时间。

**语法:**

```sql
YEAR(date)
```

**参数:**
该方法只接受一个参数，如下所示:

*   **日期:**指定的归还年份的起始日期。

**返回:**
返回指定日期的年份。

**示例-1 :**
使用 YEAR()函数，从指定日期开始获取年份。

```sql
SELECT YEAR('2020/01/02');
```

**输出:**

```sql
2020
```

**示例-2 :**
使用带有变量的 YEAR()函数，从指定日期获取年份。

```sql
DECLARE @date VARCHAR(50);
SET @date = '2017/07/05';
SELECT YEAR(@date);
```

**输出:**

```sql
2017
```

**示例-3 :**
使用 YEAR()函数，以日期为参数，其中还包括时间。

```sql
SELECT YEAR('2018/11/22 07:44');
```

**输出:**

```sql
2018
```

**示例-4 :**
使用带有变量和日期的 YEAR()函数作为参数，其中还包括时间。

```sql
DECLARE @date VARCHAR(50);
SET @date = '1995/05/13 23:59';
SELECT YEAR(@date);
```

**输出:**

```sql
1995
```

**应用:**
此功能用于查找指定日期的年份。