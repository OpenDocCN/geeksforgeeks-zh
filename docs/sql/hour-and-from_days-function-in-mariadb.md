# Mariadb 中的 HOUR()和 FROM_DAYS()函数

> 原文:[https://www . geesforgeks . org/hour-and-from _ days-function-in-mariadb/](https://www.geeksforgeeks.org/hour-and-from_days-function-in-mariadb/)

**1。HOUR()函数:**
在马里亚数据库中，HOUR()函数用于返回日期值的小时部分。在这个函数中，第一个参数是 date_value。该函数将返回给定日期的 HOUR 部分。因为时间值的范围可以从-838:59:59’到‘838:59:59’，所以这个函数可以返回值 0 到 838。

**语法:**

```sql
HOUR(date_value)
```

**参数:**

*   **日期值–**从中提取小时部分的日期时间值。

**返回:**日期的小时部分。

**示例-1 :**

```sql
SELECT HOUR('2020-05-09 06:11:18.000004');
```

**输出:**

```sql
6
```

**示例-2 :**

```sql
SELECT HOUR('837:56:52');
```

**输出:**

```sql
837
```

**示例-3 :**

```sql
SELECT HOUR('2018-02-11 11:19:01');
```

**输出:**

```sql
11
```

**示例-4 :**

```sql
SELECT HOUR('10:02:06');
```

**输出:**

```sql
10
```

**示例-5:**CURTIME()函数返回当前系统时间。

```sql
SELECT HOUR(CURTIME());
```

**输出:**

```sql
8
```

**2。FROM_DAYS()函数:**
在马里亚数据库中，FROM_DAYS()函数用于将数字日转换为日期值。在这个函数中，第一个参数是日期。该函数将给定的数字转换为日期。此功能仅适用于公历中的日期。

**语法:**

```sql
FROM_DAYS(date)
```

**参数:**

*   **日期–**将转换为日期值的日期(数字)。

**返回:**日期值。

**示例-1 :**

```sql
SELECT FROM_DAYS(735919) ;
```

**输出:**

```sql
'2014-11-17'
```

**示例-2 :**

```sql
SELECT (FROM_DAYS(780500)- FROM_DAYS(780500));
```

**输出:**

```sql
0
```

**示例-3 :**

```sql
SELECT FROM_DAYS(735910);
```

**输出:**

```sql
'2014-11-08'
```