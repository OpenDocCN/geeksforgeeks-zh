# MySQL 中的 MINUTE()函数

> 原文:[https://www.geeksforgeeks.org/minute-function-in-mysql/](https://www.geeksforgeeks.org/minute-function-in-mysql/)

**MINUTE()函数:**
[MySQL](https://www.geeksforgeeks.org/sql-tutorial/)中的该函数用于返回指定时间或日期时间值的分钟部分。分钟值的范围是从 0 到 59。例如，如果指定的时间是“09:12:23”，该函数将返回 12 分钟。

**语法:**

```sql
MINUTE(datetime)
```

**参数:**
该方法接受如下参数。

*   **日期时间–**提取分钟的指定时间或日期时间值。

**返回:**
返回指定时间或日期时间值的分钟部分。

**例-1 :**
从指定日期和时间“2020-11-24 09:32:12”获取分钟“32”。

```sql
SELECT MINUTE("2020-11-24 09:32:12");
```

**输出:**

```sql
32
```

**示例-2 :**
从指定时间“06:12:23”获取分钟“12”。

```sql
SELECT MINUTE("06:12:23");
```

**输出:**

```sql
12
```

**例-3 :**
从指定时间“838:59:59”获取分钟“59”。

```sql
SELECT MINUTE("838:59:59");
```

**输出:**

```sql
59
```

**应用:**
该功能用于返回指定时间或日期的分钟部分时间值。