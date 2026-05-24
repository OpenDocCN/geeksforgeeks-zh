# MySQL 中的微秒()函数

> 原文:[https://www . geesforgeks . org/微秒-函数 in-mysql/](https://www.geeksforgeeks.org/microsecond-function-in-mysql/)

**微秒():**

[MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中的这个函数用于返回指定时间或日期时间值的微秒部分。微秒值的范围是从 0 到 999999。例如，如果指定的时间是“09:12:23.000123”，该函数将返回 123 微秒。

**语法:**

```sql
MICROSECOND(datetime)
```

**参数:**

此方法接受如下参数:

*   **DateTime–** The specified time or datetime value from which microseconds are to be extracted.

**返回:**

它返回指定时间或日期时间值的微秒部分。

**示例-1 :**

从指定的日期和时间“2020-11-24 09:32:12.000222”获取微秒“222”，如下所示。

```sql
SELECT MICROSECOND("2020-11-24 09:32:12.000222");
```

**输出:**

```sql
222
```

**示例-2 :**

从指定时间“06:12:23.123456”获取微秒“123456”，如下所示。

```sql
SELECT MICROSECOND("06:12:23.123456");
```

**输出:**

```sql
123456
```

**示例-3 :**

从指定时间“838:9:19.999999”获取微秒“999999”，如下所示。

```sql
SELECT MICROSECOND("838:9:19.999999");
```

**输出:**

```sql
999999
```

**示例-4 :**

从指定时间“1:2:7.9”获取微秒“900000”，如下所示。

```sql
SELECT MICROSECOND("1:2:7.9");
```

**输出:**

```sql
900000
```

**示例-5 :**

从指定时间“16:24:0.070”获取微秒“70000”，如下所示。

```sql
SELECT MICROSECOND("16:24:0.070");
```

**输出:**

```sql
70000
```

**示例-6 :**

从指定时间“12:32:52.000023”获取微秒“23”，如下所示。

```sql
SELECT MICROSECOND("12:32:52.000023");
```

**输出:**

```sql
23
```

**应用:**

该函数用于返回指定时间或日期时间值的微秒部分。