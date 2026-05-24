# SQL Server 中的 DATEDIFF()函数

> 原文:[https://www . geesforgeks . org/datediff-function-in-SQL-server/](https://www.geeksforgeeks.org/datediff-function-in-sql-server/)

**DATEDIFF()函数:**
SQL Server 中的这个函数是用来查找两个指定日期的差异。

**特征:**

*   该函数用于查找两个给定日期值之间的差异。
*   该功能属于日期功能。
*   该函数接受三个参数，即间隔、第一个日期值和第二个日期值。
*   该函数可以在时间间隔部分和日期值部分包含时间。

**语法:**

```sql
DATEDIFF(interval, date1, date2)

```

**参数:**
该方法接受如下三个参数:

*   **间隔:**是要退回的指定部分。此外，区间的值可以如下给出:

1.  年份，yyyy，yy = Year，这是指定的年份。
2.  季度，qq，q = Quarter，这是指定的季度。
3.  月，mm，m =月，即指定的月份。
4.  dayofyear，dy，y =一年中的某一天，这是一年中指定的一天。
5.  day，dd，d = Day，这是指定的日期。
6.  week，ww，wk = Week，这是指定的一周。
7.  weekday，dw，w = Weekday，这是指定的星期几。
8.  小时，hh =小时，这是指定的小时。
9.  分钟，mi，n =分钟，这是指定的分钟。
10.  second，ss，s = Second，这是指定的秒。
11.  毫秒，ms =毫秒，这是指定的毫秒。

*   **日期 1、日期 2 :** 两个指定的日期，以便找出它们之间的区别。

**返回:**
返回两个指定日期的差值。

**示例-1 :**
使用 DATEDIFF()函数并获取两个日期值之间的差值，单位为年。

```sql
SELECT DATEDIFF(year, '2010/01/12', '2021/01/12');

```

**输出:**

```sql
11
```

**示例-2 :**
使用 DATEDIFF()函数并获取两个日期值之间的差值，以月为单位。

```sql
SELECT DATEDIFF(month, '2010/2/12', '2021/12/12');

```

**输出:**

```sql
142
```

**示例-3 :**
使用 DATEDIFF()函数并获取两个日期值之间的负差，单位为天。

```sql
SELECT DATEDIFF(day, '2021/2/1', '2010/12/12');

```

**输出:**

```sql
-3704
```

**示例-4 :**
使用 DATEDIFF()函数，得到两个日期值之间的差值，其中也包括时间，单位为小时。

```sql
SELECT DATEDIFF(hour, '2019/2/1 09:55', '2020/12/12 07:45');

```

**输出:**

```sql
16318
```

**示例-5 :**
使用 DATEDIFF()函数，并使用包含时间的变量获得两个日期值之间的差值，单位为秒。

```sql
DECLARE @date1 VARCHAR(50);
DECLARE @date2 VARCHAR(50);
SET @date1 = '2019/2/1 09:55:44';
SET @date2 = '2020/12/12 07:45:22';
SELECT DATEDIFF(second, @date1, @date2);

```

**输出:**

```sql
58744178
```

**应用:**
此函数用于查找两个指定日期值之间的差异。