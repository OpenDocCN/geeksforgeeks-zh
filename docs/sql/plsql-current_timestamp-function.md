# PLSQL | CURRENT_TIMESTAMP 函数

> 原文:[https://www . geesforgeks . org/plsql-current _ timestamp-function/](https://www.geeksforgeeks.org/plsql-current_timestamp-function/)

**PLSQL CURRENT_TIMESTAMP** 函数用于返回会话时区的当前日期和时间。使用的时区是由 ALTER SESSION 命令设置的当前 SQL 会话的时区。函数的作用是:返回一个带时区的时间戳值，而函数的作用是:返回一个不带时区数据的日期值。
CURRENT _ TIMESTAMP 函数不接受任何参数。

**语法:**

```sql
CURRENT_TIMESTAMP
```

**使用的参数:**
CURRENT _ TIMESTAMP 函数不接受任何参数。

**返回值:**
CURRENT _ TIMESTAMP 函数返回 TIMESTAMP WITH TIME ZONE 数据类型中当前时间戳的值。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:** 使用 CURRENT_TIMESTAMP 函数显示会话时区中的当前时间戳。

```sql
ALTER SESSION SET NLS_DATE_FORMAT = 'DD-MON-YYYY HH24:MI:SS';

SELECT
  CURRENT_TIMESTAMP
FROM
  dual; 
```

**输出:**

```sql
Session altered.

CURRENT_TIMESTAMP
22-OCT-19 07.28.32.374935 AM +00:00 
```

**示例-2:** 使用 CURRENT_TIMESTAMP 函数使用更改的会话时区显示当前时间戳。

```sql
ALTER SESSION SET TIME_ZONE = '-10:00';

SELECT
  CURRENT_TIMESTAMP
FROM
  dual; 
```

**输出:**

```sql
Session altered.

CURRENT_TIMESTAMP
21-OCT-19 09.31.40.273270 PM -10:00 
```

新的日期和时间按预期调整了约-10 小时。

**优势:**
CURRENT _ TIMESTAMP 函数返回带时区的时间戳值，而 CURRENT_DATE 函数返回不带时区数据的日期值。