# 【SYSDATE 函数在 PL/SQL 中如何工作

> 原文:[https://www . geesforgeks . org/how-sysdate-function-works-in-pl-SQL/](https://www.geeksforgeeks.org/how-sysdate-function-works-in-pl-sql/)

函数将返回数据库中当前的系统日期和时间。SYSDATE 函数没有任何参数或参数。函数的作用是:返回一个日期值。请注意，SYSDATE 函数返回的日期和时间为“YYYY-MM-DD HH:MM:SS”(字符串)或 YYYYMMDDHHMMSS(数字)。

**语法:**

```sql
SYSDATE

```

**示例-1:**

```sql
SELECT Sysdate AS System_date
FROM Dual
```

**说明:**
以上示例将显示数据库中系统的当前日期。它将从 dual 执行语法“Sysdate”，该语法充当虚拟表，并且只以默认格式显示日期。在上述查询中，“系统 _ 日期”作为**别名**，即该指定列的临时名称。

**输出:**

| 系统日期 |
| 2019-01-05 |

**1。显示日期和时间–**

**语法:**

```sql
SELECT TO_CHAR(Sysdate, Format_Of_Date_and_Time) AS Alias_Name
FROM Dual 

Format_Of_Date_and_Time:
DD-MM-YYYY HH:MM:SS
MM-DD-YYYY HH:MM:SS
YYYY-MM-DD HH:MM:SS
DD-MON-YYYY HH:MM:SS
MON-DD-YY HH:MM:SS
DD-MM-YYYY HH24:MM:SS (For 24hr time Format) 
```

**示例-2:**

```sql
SELECT TO_CHAR (Sysdate, 'DD-MM-YYYY HH24:MI:SS') AS System_date_time
FROM Dual
```

**输出:**

| 系统 _ 日期 _ 时间 |
| 05-01-2019 09:45:51 |

**示例-3:**

```sql
SELECT TO_CHAR (Sysdate, 'YYYY-MON-DD HH24:MI:SS') AS System_date_time
FROM Dual
```

**输出:**

| 系统 _ 日期 _ 时间 |
| 2019-JAN-05 09:45:51 |

**说明:**
在上面的例子中，它会以指定的格式显示数据库中的日期和时间。 **TO_CHAR()** 功能基本上有助于将系统日期转换为指定格式的日期和时间。此处的“系统日期时间”也用作别名，并在定义的列中显示日期和时间。

**2。使用级别显示从当前日期开始的连续日期–**

**语法:**

```sql
SELECT Sysdate+Level-1
FROM Dual
CONNECT BY Level<=n 
```

其中 n 是连续天数。

**示例-4:**

```sql
SELECT Sysdate+Level-1 AS Consecutive_dates
FROM Dual
CONNECT BY Level<=5
```

**说明:**
为了显示连续的日期数，我们可以使用 **SYSDATE** 和 **LEVEL** 。级别可以用作分层结构，具有像 1 作为根，然后 2 作为子，然后 3 这样的子节点。级别的初始值为 1，这里系统日期与级别相加，作为多级结构，这样有助于以连续的方式显示日期。

**输出:**

| 连续 _ 日期 |
| 2019-01-05 |
| 2019-01-06 |
| 2019-01-07 |
| 2019-01-08 |
| 2019-01-09 |