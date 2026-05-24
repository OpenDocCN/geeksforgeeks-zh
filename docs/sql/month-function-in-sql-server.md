# SQL Server 中的 MONTH()函数

> 原文:[https://www.geeksforgeeks.org/month-function-in-sql-server/](https://www.geeksforgeeks.org/month-function-in-sql-server/)

**MONTH()函数:**
SQL Server 中的这个函数用来返回一年中的月份，即从 1 到 12 的某个指定日期。

**特征:**

*   该函数用于查找指定日期的月份。
*   该功能属于日期功能。
*   该函数只接受一个参数，即日期。
*   该功能还可以包括带有规定日期的时间。

**语法:**

```sql
MONTH(date)
```

**参数:**
该方法只接受一个参数，如下所示:

*   **日期:**指定的日期，从该日期开始返回一年中的月份。

**返回:**
返回一年中的月份，即从 1 到 12 的指定日期。

**示例-1 :**
使用 MONTH()函数，从指定的日期获取一年中的月份。

```sql
SELECT MONTH('2020/01/02');
```

**输出:**

```sql
1
```

**示例-2 :**
使用带变量的 MONTH()函数，从指定日期获取一年中的月份。

```sql
DECLARE @date VARCHAR(50);
SET @date = '2020/07/05';
SELECT MONTH(@date);
```

**输出:**

```sql
7
```

**示例-3 :**
使用以日期为参数的 MONTH()函数，该函数还包括时间。

```sql
SELECT MONTH('2018/11/22 07:44');
```

**输出:**

```sql
11
```

**示例-4 :**
使用带有变量和日期的 MONTH()函数作为参数，其中还包括时间。

```sql
DECLARE @date VARCHAR(50);
SET @date = '2020/09/30 23:59';
SELECT MONTH(@date);

```

**输出:**

```sql
9
```

**应用:**
此功能用于从指定日期开始查找一年中的月份。