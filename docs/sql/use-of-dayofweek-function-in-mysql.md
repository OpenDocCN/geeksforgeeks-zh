# 在 MySQL 中使用 DAYOFWEEK()函数

> 原文:[https://www . geesforgeks . org/use-of-dayofweek-function-in-MySQL/](https://www.geeksforgeeks.org/use-of-dayofweek-function-in-mysql/)

**DAYOFWEEK():**
MySQL 中的这个函数有助于返回给定日期的工作日数字/索引(1 到 7 之间的数字)。DAYOFWEEK()函数返回的工作日索引遵循 ODBC 标准。

**注–**
以下为工作日数字。

```sql
Sunday
Monday
Tuesday
Wednesday
Thursday
Friday
Saturday

```

**语法:**

```sql
DAYOFWEEK(date)

```

**参数:**
函数只接受一个参数。

*   **日期–**
    返回工作日索引的日期或日期时间

**返回:**

*   该函数将返回给定日期的工作日数字/索引(从 1 到 7 的数字)。
*   如果日期为零(0000-00-00)或无效，在这种情况下，函数将返回空值。

**示例-1 :**
从特定日期“2020-09-13”获取星期几。

```sql
SELECT DAYOFWEEK("2020-09-13") 
AS WEEKDAY;
```

**输出:**

| 工作日 |
| one |

**示例-2 :**
从特定的日期时间“2000-11-27 07:12:23”中获取一周中的某一天。

```sql
SELECT DAYOFWEEK("2000-11-02 07:12:23") 
AS WEEKDAY;
```

**输出:**

| 工作日 |
| five |

**示例-3 :**
获取当前系统日期的星期几，即使用 CURDATE()函数

```sql
SELECT DAYOFWEEK(CURDATE()) 
AS WEEKDAY;
```

**输出:**

| 工作日 |
| four |