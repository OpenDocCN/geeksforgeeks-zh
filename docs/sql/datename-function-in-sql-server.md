# SQL Server 中的 DATENAME()函数

> 原文:[https://www . geesforgeks . org/datename-function-in-SQL-server/](https://www.geeksforgeeks.org/datename-function-in-sql-server/)

**DATENAME()功能:**

SQL Server 中的这个[函数用于查找指定日期的给定部分。此外，它以字符串形式返回输出值。](https://www.geeksforgeeks.org/aggregate-functions-in-sql/)

**功能:**

*   This function is used to find the given part of the specified date.
*   This function belongs to the date function.
*   This function accepts two parameters, namely interval and date.
*   This function can also include the time in the date part.
*   This function returns the output as a string.

**语法:**

```sql
DATENAME(interval, date)
```

**参数:**

该方法接受两个参数，如下所示。

*   **interval–** is the designated part to be returned. In addition, the value of the interval can be given as follows.

```sql
year, yyyy, yy   = Year, which is the specified year.
quarter, qq, q   = Quarter, which is the specified quarter.
month, mm, m     = month, which is the specified month.
dayofyear, dy, y = Day of the year, which is the specified day of the year.
day, dd, d       = Day, which is the specified day.
week, ww, wk     = Week, which is the specified week.
weekday, dw, w   = Weekday, which is the specified week day.
hour, hh         = hour, which is the specified hour.
minute, mi, n    = Minute, which is the specified minute.
second, ss, s    = Second, which is the specified second.
millisecond, ms  = Millisecond, which is the specified millisecond.
```

*   **Date–** is the specified date to be used.

**返回:**

它返回指定日期的给定部分。

**示例-1 :**

使用 DATENAME()函数并获取指定日期的年份部分。

```sql
SELECT DATENAME(year, '2021/01/06');
```

**输出:**

```sql
2021
```

**示例-2 :**

使用 DATENAME()函数并获取指定日期的月份部分。

```sql
SELECT DATENAME(month, '2021/01/06');
```

**输出:**

```sql
January
```

**示例-3 :**

使用 DATENAME()函数并获取指定日期的日部分。

```sql
SELECT DATENAME(day, '2021/01/06');
```

**输出:**

```sql
6
```

**示例-4 :**

使用 DATENAME()函数并获取指定日期的小时部分，其中也包括时间。

```sql
SELECT DATENAME(hour, '2021/01/06 05:30');
```

**输出:**

```sql
5
```

**示例-5 :**

使用 DATENAME()函数并获取指定日期的第二部分，其中包括时间以及使用变量。

```sql
DECLARE @date VARCHAR(50);
SET @date = '2019/06/05 07:37:54';
SELECT DATENAME(second, @date);
```

**输出:**

```sql
54
```

**应用:**

该函数用于查找指定日期的给定部分。