# MariaDB 中的 TIME 和 TIME_TO_SEC 函数

> 原文：[https://www.geeksforgeeks.org/time-and-time_to_sec-function-in-mariadb/](https://www.geeksforgeeks.org/time-and-time_to_sec-function-in-mariadb/)

## TIME 函数

在 MariaDB 中，`TIME()` 函数返回日期时间表达式的时间部分。该函数接受一个日期时间表达式作为参数，并返回其时间部分。如果表达式不是时间或日期时间值，`TIME()` 函数将返回 `'00:00:00'`。如果表达式为 `NULL`，则函数返回 `NULL`。

**语法：**

```sql
TIME( expression )
```

**参数：**

*   `expression` – 一个日期时间值，将从中提取时间。

**返回值：**
返回日期时间表达式的时间部分。

**示例 1：**

```sql
SELECT TIME('2020-10-16 06:18:01.000001');
```

**输出：**

```sql
'06:18:01.000001'
```

**示例 2：**

```sql
SELECT TIME('10:35:05');
```

**输出：**

```sql
10:35:05
```

**示例 3：**

```sql
SELECT TIME(NULL);
```

**输出：**

```sql
NULL
```

## TIME_TO_SEC 函数

在 MariaDB 中，`TIME_TO_SEC()` 函数用于将时间值转换为秒数。该函数接受一个时间值作为参数，并返回其对应的数字秒数。其功能与 `SEC_TO_TIME()` 函数相反。

**语法：**

```sql
TIME_TO_SEC( time )
```

**参数：**

*   `time` – 一个时间值，将被转换为秒数。

**返回值：**
返回以秒为单位的数字。

**示例 1：**

```sql
SELECT TIME_TO_SEC('00:00:02');
```

**输出：**

```sql
2
```

**示例 2：**

```sql
SELECT TIME_TO_SEC('00:00:01.999999');
```

**输出：**

```sql
1.999999
```

**示例 3：**

```sql
SELECT TIME_TO_SEC('-12:30:59');
```

**输出：**

```sql
-45059
```