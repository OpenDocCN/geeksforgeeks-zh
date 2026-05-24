# SQL Server 中的 DAY()函数

> 原文:[https://www.geeksforgeeks.org/day-function-in-sql-server/](https://www.geeksforgeeks.org/day-function-in-sql-server/)

**DAY()函数:**
SQL Server 中的这个函数用于返回一个月中的某一天，即所述日期的 1 号到 31 号。

**特征:**

*   该函数用于查找指定日期的月份。
*   该功能属于日期功能。
*   该功能只接受一个参数，即*日期*。
*   该功能还可以包括带有规定日期的时间。

**语法:**

```sql
DAY(date)
```

**参数:**
该方法只接受一个参数，如下所示。

*   **日期–**返回当月日期的指定日期。

**返回:**
返回一个月中的某一天，即从 1 日到 31 日的指定日期。

**示例-1 :**
使用 DAY()函数，从指定的日期获取当月的某一天。

```sql
SELECT DAY('2020/01/02');
```

**输出:**

```sql
2
```

**示例-2 :**
使用带变量的 DAY()函数，从指定的日期获取当月的某一天。

```sql
DECLARE @date VARCHAR(50);
SET @date = '2020/01/05';
SELECT DAY(@date);
```

**输出:**

```sql
5
```

**示例-3 :**
使用 DAY()函数，以日期为参数，其中还包括时间。

```sql
SELECT DAY('2018/11/22 07:44');
```

**输出:**

```sql
22
```

**示例-4 :**
使用带有变量和日期的 DAY()函数作为参数，其中还包括时间。

```sql
DECLARE @date VARCHAR(50);
SET @date = '2020/11/30 23:59';
SELECT DAY(@date);
```

**输出:**

```sql
30
```

**应用:**
此功能用于从指定日期开始查找当月的某一天。