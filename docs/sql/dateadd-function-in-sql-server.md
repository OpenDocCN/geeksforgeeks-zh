# SQL Server 中的 DATEADD()函数

> 原文:[https://www . geesforgeks . org/dateadd-function-in-SQL-server/](https://www.geeksforgeeks.org/dateadd-function-in-sql-server/)

**DATEADD()函数:**
SQL Server 中的这个函数用来将一个时间或一个日期间隔加总到一个指定的日期，然后返回修改后的日期。

**特征:**

*   该函数用于将时间或日期间隔与指定日期相加。
*   该功能属于日期功能。
*   该函数接受三个参数，即间隔、数字和日期。
*   该功能还可以在间隔部分包括时间。

**语法:**

```sql
DATEADD(interval, number, date)
```

**参数:**
该方法接受如下三个参数。

*   **间隔–**
    是要添加的指定时间或日期间隔。此外，区间的值可以如下给出。

    ```sql
    year, yyyy, yy   = Year, which is the specified year to be added.
    quarter, qq, q   = Quarter, which is the specified quarter to be added.
    month, mm, m     = month, which is the specified month to be added.
    dayofyear, dy, y = Day of the year, which is the specified day of the year to be added.
    day, dd, d       = Day, which is the specified day to be added.
    week, ww, wk     = Week, which is the specified week to be added.
    weekday, dw, w   = Weekday, which is the specified week day to be added.
    hour, hh         = hour, which is the specified hour to be added.
    minute, mi, n    = Minute, which is the specified minute to be added.
    second, ss, s    = Second, which is the specified second to be added.
    millisecond, ms  = Millisecond, which is the specified millisecond to be added.

    ```

*   **数字–**
    是要添加到指定日期的间隔数。它可以是正的，以便得到未来的日期，也可以是负的，以便得到过去的日期。
*   **日期–**
    是要更改的指定日期。

**返回:**
在规定日期上增加日期或时间间隔后，返回修改后的日期。

**例-1 :**
使用 DATEADD()函数，加上日期的年份部分，得到修改日期。

```sql
SELECT DATEADD(year, 2, '2019/01/05');
```

**输出:**

```sql
2021-01-05 00:00:00.000
```

**示例-2 :**
使用 DATEADD()函数，添加日期的月份部分，得到修改日期。

```sql
SELECT DATEADD(month, 11, '2019/01/05');

```

**输出:**

```sql
2019-12-05 00:00:00.000
```

**示例-3 :**
使用 DATEADD()函数，减去日期的月份部分，得到修改日期。

```sql
SELECT DATEADD(month, -1, '2019/01/05');

```

**输出:**

```sql
2018-12-05 00:00:00.000
```

**示例-4 :**
使用 DATEADD()函数并添加日期中的天部分以获取修改日期。

```sql
SELECT DATEADD(day, 32, '2015/04/14');
```

**输出:**

```sql
2015-05-16 00:00:00.000
```

**例-5 :**
使用 DATEADD()函数，加上日期的分钟部分，得到修改日期。

```sql
SELECT DATEADD(minute, 6, '2015/04/14 09:55');

```

**输出:**

```sql
2015-04-14 10:01:00.000
```

**示例-6 :**
使用 DATEADD()函数，并使用变量添加日期的小时部分，以获取修改后的日期。

```sql
DECLARE @number INT;
SET @number = 8;
SELECT 
DATEADD(hh, @number, '2021/01/02 08:50');
```

**输出:**

```sql
2021-01-02 16:50:00.000
```

**示例-7 :**
使用 DATEADD()函数并添加日期的第二部分使用变量获取修改日期。

```sql
DECLARE @number INT;
DECLARE @date VARCHAR(50);
SET @number = 08;
SET @date = '2011/11/22 07:59:56';
SELECT 
DATEADD(ss, @number, @date);
```

**输出:**

```sql
2011-11-22 08:00:04.000
```

**应用:**
该功能用于在规定日期上增加日期或时间间隔后，查找修改日期。