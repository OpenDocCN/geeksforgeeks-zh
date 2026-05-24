# PLSQL | CURRENT_DATE 函数

> 原文:[https://www.geeksforgeeks.org/plsql-current_date-function/](https://www.geeksforgeeks.org/plsql-current_date-function/)

**PLSQL CURRENT_DATE** 功能用于返回会话时区的当前日期。使用的时区是由 ALTER SESSION 命令设置的当前 SQL 会话的时区。PLSQL CURRENT_DATE 函数使用数据类型 DATE 的公历值。
CURRENT _ DATE 函数不接受任何参数。

**语法:**

```sql
CURRENT_DATE
```

**使用的参数:**
CURRENT _ DATE 函数不接受任何参数。

**返回值:**
CURRENT _ DATE 函数返回一个日期值。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:** 使用 SESSIONTIMEZONE 函数查找会话时区。

```sql
ALTER SESSION SET NLS_DATE_FORMAT = 'DD-MON-YYYY HH24:MI:SS';

SELECT
  SESSIONTIMEZONE
FROM
  DUAL; 
```

**输出:**

```sql
Session altered.

SESSIONTIMEZONE
+00:00 
```

**示例-2:** 使用 CURRENT_DATE 函数获取会话时区的当前日期。

```sql
ALTER SESSION SET NLS_DATE_FORMAT = 'DD-MON-YYYY HH24:MI:SS';

SELECT
  SESSIONTIMEZONE
FROM
  DUAL;

SELECT
  CURRENT_DATE
FROM
  DUAL; 
```

**输出:**

```sql
Session altered.

SESSIONTIMEZONE
+00:00

CURRENT_DATE
22-OCT-2019 06:53:58 
```

**示例-3:** 更改会话时区后使用 CURRENT_DATE 函数获取当前日期。

```sql
ALTER SESSION SET NLS_DATE_FORMAT = 'DD-MON-YYYY HH24:MI:SS';

SELECT
  SESSIONTIMEZONE
FROM
  DUAL;

ALTER SESSION SET TIME_ZONE = '-02:00';

SELECT
  CURRENT_DATE
FROM
  DUAL; 
```

**输出:**

```sql
Session altered.

SESSIONTIMEZONE
+00:00

Session altered.

CURRENT_DATE
22-OCT-2019 05:05:36 
```

新的当前日期按预期调整了约-2 小时。