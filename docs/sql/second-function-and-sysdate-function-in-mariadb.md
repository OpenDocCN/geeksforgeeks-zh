# 马里亚数据库中的第二功能和系统日期功能

> 原文:[https://www . geesforgeks . org/second-function-and-sysdate-function-in-mariadb/](https://www.geeksforgeeks.org/second-function-and-sysdate-function-in-mariadb/)

**1。第二个函数:**
在马里亚数据库中，第二个函数返回日期值的第二部分。在这个函数中，第一个参数是日期/日期时间。该函数返回给定日期值的秒(0 到 59 之间的数字)。在这个函数中，我们将在其中传递日期值，它将返回第二个日期作为结果。

**语法:**

```sql
SECOND( date_value )
```

**参数:**

*   **date _ value–**从中提取第二个的日期或日期时间值。

**返回:**

它将返回日期值的第二部分。

**示例-1:**

```sql
SELECT SECOND('10:06:23')-SECOND('2020-05-19 09:19:02.000004');
```

**输出:**

```sql
21
```

**示例-2:**

```sql
SELECT SECOND('01:02:22')+SECOND('02:10:06');
```

**输出:**

```sql
28
```

**示例-3:**

```sql
SELECT SECOND('14:01:26');
```

**输出:**

```sql
26
```

**示例-4:**

```sql
SELECT SECOND('2020-05-19 09:19:02.000004');
```

**输出:**

```sql
2
```

**示例-5:**

```sql
SELECT SECOND('2018-10-11 12:20:23');
```

**输出:**

```sql
23
```

**示例-6:**

```sql
SELECT SECOND('838:10:59');
```

**输出:**

```sql
59
```

**示例-7:**

```sql
#The Curdate() function will return the current time of the system date
SELECT SECOND(CURDATE());
```

**输出:**

```sql
19
```

**2。**
在马里亚数据库中，系统日期函数用于返回当前日期和时间。在这个函数中，不会传递任何参数。对于字符串上下文，此函数将以“YYYY-MM-DD HH:MM: SS”格式返回当前日期。对于数字上下文，该函数将以 YYYYMMDDHHMMSS 格式返回当前日期。

**语法:**

```sql
SYSDATE()
```

**参数:**

*   **NA–**该函数中不会传递任何参数。

**返回:**

返回当前日期和时间

**示例-1:**

```sql
SELECT (SYSDATE()+12)-SYSDATE();
```

**输出:**

```sql
12
```

**示例-2:**

```sql
SELECT SYSDATE();
```

**输出:**

```sql
'2020-11-08 10:27:21'
```

**示例-3:**

```sql
SELECT SYSDATE() + 10;
```

**输出:**

```sql
20201108102731
```

**示例-4:**

```sql
SELECT SYSDATE() - 15;
```

**输出:**

```sql
20201108102706
```