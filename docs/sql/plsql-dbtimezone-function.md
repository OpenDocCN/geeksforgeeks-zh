# PLSQL | DBTIMEZONE 功能

> 原文:[https://www.geeksforgeeks.org/plsql-dbtimezone-function/](https://www.geeksforgeeks.org/plsql-dbtimezone-function/)

**PLSQL DBTIMEZONE** 函数用于返回数据库时区值。PLSQL DBTIMEZONE 函数不需要传递任何参数。DBTIMEZONE 函数返回一个时区偏移量，它遵循的格式是“[+|-]TZH:TZM，例如-05:00。它还可能返回时区区域名称，例如，某些设备上的美国/密歇根州。

DBTYPE 函数返回的值取决于它在最近的 CREATE DATABASE 或 ALTER DATABASE 语句中的指定方式。

**语法:**

```sql
DBTIMEZONE
```

**使用的参数:**
dbtime zone 函数不接受任何参数。

**返回值:**
PLSQL 中的 DBTIMEZONE 函数返回时区偏移量或时区区域名称。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:** 显示数据库时区。

```sql
SELECT
  DBTIMEZONE
FROM
  dual; 
```

**输出:**

```sql
+00:00 
```

该函数也可以返回任何其他值，因为它完全取决于用户设备中设置的时区值。

**示例-2:** 使用 ALTER 语句更改数据库时区后显示该时区。<

```sql
ALTER DATABASE SET TIME_ZONE = ‘US/Michigan’;

SELECT
  DBTIMEZONE
FROM
  dual; 
```

**输出:**

```sql
US/Michigan 
```