# MySQL 中的 SECOND()函数

> 原文:[https://www.geeksforgeeks.org/second-function-in-mysql/](https://www.geeksforgeeks.org/second-function-in-mysql/)

[MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中的 SECOND()函数用于返回指定时间或日期时间值的第二部分。该函数的第一个参数是日期/日期时间。该函数返回给定日期值的秒数。返回值(秒)将在 0 到 59 的范围内。在这个函数中，我们将在其中传递日期值，它将返回第二个日期作为结果。例如，如果指定的时间是“09:12:23”，那么该函数将返回“23”。

**功能:**

*   This function is used to find the second part of the specified time or datetime value.
*   This function accepts a single parameter.
*   The accepted parameter is date/datetime.
*   This function returns a second value between 0 and 59.

**语法:**

```sql
SECOND(date_value)
```

**参数:**该方法接受如下所示的参数:

**date_value:** 指定时间或日期时间值提取秒。

**返回:**返回指定时间或日期时间值的第二部分。

**应用:**该功能用于返回指定时间或日期的第二部分时间值。

**例 1:** 从指定日期时间“2020-11-24 09:32:12”获取结果“12”。

```sql
SELECT SECOND("2020-11-24 09:32:12");
```

**输出:**

```sql
12
```

**例 2:** 从指定日期时间“2021-12-20 02:24:30”获取结果“30”。

```sql
SELECT SECOND("2021-12-20 02:24:30");
```

**输出:**

```sql
30
```

**例 3:** 从指定时间“06:12:23”获取结果“23”。

```sql
SELECT SECOND("06:11:23");
```

**输出:**

```sql
23
```

**例 4:** 从指定时间“23:12:59”得到结果“59”。

```sql
SELECT SECOND("23:12:59");
```

**输出:**

```sql
59
```

**示例 5:** 从日期时间获取结果“16”。函数“POWER(2，4)”返回了参数日期时间值“16”，而 SECOND()函数将该值“16”作为参数，并将相同的值“16”作为第二个值返回。

```sql
SELECT SECOND(POWER(2, 4));
```

**输出:**

```sql
16
```

**例 6:** 获取当前时间的结果。这将返回当前系统时间的第二部分。例如，如果当前系统时间为“06:12:23”，则结果将返回“23”。

```sql
SELECT SECOND(CURTIME());
```

**输出:**

```sql
23
```

**示例 7:** 从系统日期获取结果。这将返回系统日期的第二部分。例如，如果系统日期为“2021-02-05 12:41:26”，则结果将返回“26”。

```sql
SELECT SECOND(SYSDATE());
```

**输出:**

```sql
26
```