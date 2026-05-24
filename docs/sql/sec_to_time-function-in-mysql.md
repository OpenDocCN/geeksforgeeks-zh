# MySQL 中的 SEC_TO_TIME()函数

> 原文:[https://www . geesforgeks . org/sec _ to _ time-function-in-MySQL/](https://www.geeksforgeeks.org/sec_to_time-function-in-mysql/)

**SEC_TO_TIME()函数:**
此函数在 [MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中用于返回基于指定秒值的时间值。这里返回的时间值将采用 HH:MM:SS 的格式。例如，如果指定的第二个值是 63，该函数将返回“00:01:03”。

**语法:**

```sql
SEC_TO_TIME(seconds)

```

**参数:**
该方法接受如下参数:

*   **秒–**指定的秒值。该值可以是正数，也可以是负数。

**返回:**
返回基于指定秒值的时间值。

**示例-1 :**
从 40 秒值的指定参数中获取时间值“00:00:40”。

```sql
SELECT SEC_TO_TIME(40);

```

**输出:**

```sql
00:00:40
```

**示例-2 :**
从 70 秒值的指定参数中获取时间值“00:01:10”。

```sql
SELECT SEC_TO_TIME(70);

```

**输出:**

```sql
00:01:10
```

**示例-3 :**
从指定的参数 3604 秒值中获取时间值“01:00:04”。

```sql
SELECT SEC_TO_TIME(3604);

```

**输出:**

```sql
01:00:04
```

**应用:**
该函数用于根据指定的秒值返回时间值。