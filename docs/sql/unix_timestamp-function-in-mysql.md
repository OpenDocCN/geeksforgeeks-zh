# MySQL 中的 UNIX_TIMESTAMP()函数

> 原文:[https://www . geesforgeks . org/UNIX _ timestamp-function-in-MySQL/](https://www.geeksforgeeks.org/unix_timestamp-function-in-mysql/)

**UNIX _ TIMESTAMP():**
MySQL 中的这个函数有助于返回一个 UNIX 时间戳。我们可以将 Unix 时间戳定义为自' 1970-01-01 00:00:00'UTC 以来经过的秒数。即使您传递了当前日期/时间或另一个指定的日期/时间，该函数也将基于此返回一个 Unix 时间戳。

**语法:**

```sql
UNIX_TIMESTAMP()
UNIX_TIMESTAMP(date)
```

**参数:**
它只接受一个参数。

*   **日期–**
    日期值，可以是日期、日期时间、时间戳或“YYYMMDD”或“YYMMDD”格式的数字。

**返回:**

*   如果未传递任何参数，该函数将以无符号整数的形式返回自' 1970-01-01 00:00:00' UTC 以来的 Unix 时间戳(以秒为单位)。
*   但是如果传递了 date 参数，该函数将以无符号整数的形式返回参数值，以 UTC ' 1970-01-01 00:00:00 '后的秒为单位。

**示例-1 :**
使用当前日期/时间运行 UNIX _ 时间戳()。

```sql
SELECT UNIX_TIMESTAMP() 
As TimeStamp; 
```

**输出:**

| 时间戳 |
| One billion six hundred and six million nine hundred and twenty-five thousand two hundred and thirty-three |

**示例-2 :**
使用日期值' 1999-01-22 '运行 UNIX _ TIMPLATE()。

```sql
SELECT UNIX_TIMESTAMP('1999-01-22') 
As TimeStamp; 
```

**输出:**

| 时间戳 |
| Nine hundred and sixteen million nine hundred and eighty-eight thousand four hundred |

**示例-3 :**
使用 DateTime 值的 UNIX_TIMESTAMP()的工作方式' 2020-10-17 02:35:43 '。

```sql
SELECT UNIX_TIMESTAMP('2020-10-17 02:35:43') 
As TimeStamp; 
```

**输出:**

| 时间戳 |
| One billion six hundred and two million nine hundred and twenty-three thousand seven hundred and forty-three |

**示例-4 :**
使用日期时间值和分数秒' 2020-10-17 02:35:43.12345 '来工作 UNIX _ 时间戳()。

```sql
SELECT UNIX_TIMESTAMP('2020-10-17 02:35:43.12345') 
As TimeStamp; 
```

**输出:**

| 时间戳 |
| 1602923743.12345 |