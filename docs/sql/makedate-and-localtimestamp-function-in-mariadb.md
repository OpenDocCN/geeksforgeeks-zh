# MariaDB 中的 MAKEDATE()和 LOCALTIMESTAMP()函数

> 原文:[https://www . geesforgeks . org/make date-and-local timestamp-function-in-mariadb/](https://www.geeksforgeeks.org/makedate-and-localtimestamp-function-in-mariadb/)

**1。MAKEDATE()函数:**
在马里亚数据库中，MAKEDATE()函数用于返回某年某月某日的日期值。在这个函数中，第一个参数是一年，第二个参数是一年中的某一天。如果一年中的某一天小于 1，MAKEDATE 函数将返回空值。

**语法:**

```sql
MAKEDATE(year, day-of-year)
```

**参数:**必选。两个参数。

*   **年份–**用于创建日期的 4 位数年份。
*   **一年中的某一天–**用于创建日期的一年中的某一天(大于 0)。

**返回:**返回某年某月某日的日期值。

**示例-1 :**

```sql
SELECT MAKEDATE(2020, 1);
```

**输出:**

```sql
'2020-01-01'
```

**示例-2 :**

```sql
SELECT MAKEDATE(2020, 42);
```

**输出:**

```sql
'2020-02-11'
```

**示例-3 :**

```sql
SELECT MAKEDATE(2019, -12);
```

**输出:**

```sql
NULL
```

**示例-4 :**

```sql
SELECT MAKEDATE(2019, 366);
```

**输出:**

```sql
'2020-01-01'
```

**示例-5 :**

```sql
SELECT MAKEDATE(2020, 366);
```

**输出:**

```sql
'2020-12-31'
```

**2。函数的作用是:**
在马里亚数据库中，函数的作用是返回当前的日期和时间。在这个函数中，不会传递任何参数。该函数将返回当前时间戳。对于字符串上下文，此函数将以“YYYY-MM-DD HH:MM: SS”格式返回当前日期。对于数字上下文，此函数将以 YYYYMMDDHHMMSS 格式返回当前日期。这个函数的工作方式类似于 LOCALTIME()函数。

**语法:**

```sql
LOCALTIMESTAMP( )
```

**参数:**不传递任何参数。

**返回:**将返回当前时间戳。

**示例-1 :**

```sql
SELECT LOCALTIMESTAMP();
```

**输出:**

```sql
'2020-10-25 12:52:35'
```

**示例-2 :** 将从当前时间戳右侧增加 10 个单位。

```sql
SELECT LOCALTIMESTAMP()+10;
```

**输出:**

```sql
'20201025125225'
```

**示例-3 :** 将从当前时间戳右侧减去 5 个单位。

```sql
SELECT LOCALTIMESTAMP()-5;
```

**输出:**

```sql
'20201025125230'
```