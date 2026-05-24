# SQL Server 中的 DATEPART()函数

> 原文:[https://www . geesforgeks . org/datepart-function-in-SQL-server/](https://www.geeksforgeeks.org/datepart-function-in-sql-server/)

**DATEPART()函数:**
此函数在 [SQL Server](https://www.geeksforgeeks.org/sql-server-identity/) 中用于查找指定日期的给定部分。此外，它以整数形式返回输出值。

**特征:**

*   该函数用于查找指定日期的给定部分。
*   该功能属于日期功能。
*   该函数接受两个参数，即间隔和日期。
*   该功能还可以在日期部分包括时间。
*   该函数以整数形式返回输出。

**语法:**

```sql
DATEPART(interval, date)
```

**参数:**
该方法接受如下两个参数。

*   **区间–**
    是要退回的指定部分。此外，区间的值可以如下给出。

```sql
year, yyyy, yy      = Year, which is the specified year.
quarter, qq, q      = Quarter, which is the specified quarter.
month, mm, m        = month, which is the specified month.
dayofyear, dy, y    = Day of the year, which is the specified day of the year.
day, dd, d          = Day, which is the specified day.
week, ww, wk        = Week, which is the specified week.
weekday, dw, w      = Weekday, which is the specified week day.
hour, hh            = hour, which is the specified hour.
minute, mi, n       = Minute, which is the specified minute.
second, ss, s       = Second, which is the specified second.
millisecond, ms     = Millisecond, which is the specified millisecond.
```

*   **日期–**
    是要使用的指定日期。

**返回:**
返回指定日期的给定部分。

**示例-1 :**

使用 DATEPART()函数并获取指定日期的年份部分。

```sql
SELECT DATEPART(year, '2017/08/25');
```

**输出:**

```sql
2017
```

**示例-2 :**
使用 DATEPART()函数，获取指定日期的月份部分。

```sql
SELECT DATEPART(month, '2017/08/25');
```

**输出:**

```sql
8
```

**示例-3 :**
使用 DATEPART()函数，获取指定日期的日部分。

```sql
SELECT DATEPART(day, '2017/08/25');
```

**输出:**

```sql
25
```

**示例-4 :**
使用 DATEPART()函数并获取指定日期的小时部分，其中也包括时间。

```sql
SELECT DATEPART(hour, '2021/01/06 05:30');
```

**输出:**

```sql
5
```

**示例-5 :**
使用 DATEPART()函数，并使用变量获取指定日期的第二部分，其中包括时间。

```sql
DECLARE @date VARCHAR(50);
SET @date = '2019/06/05 07:37:54';
SELECT DATEPART(second, @date);
```

**输出:**

```sql
54
```

**应用:**
该功能用于查找指定日期的给定部分。