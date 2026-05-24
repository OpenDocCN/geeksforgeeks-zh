# MySQL 中的 HOUR()函数

> 原文:[https://www.geeksforgeeks.org/hour-function-in-mysql/](https://www.geeksforgeeks.org/hour-function-in-mysql/)

**HOUR()函数:**
这个函数在 [MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中用来返回指定日期的小时部分。小时值的范围是从 0 到 838。对于**示例**，如果指定时间为“09:12:23”，则该功能将返回 09 小时。

**语法:**

```sql
HOUR(datetime)

```

**参数:**
该方法接受一个参数，如下图所示:

*   **日期时间–**从中提取小时的指定日期时间值。

**返回:**
返回指定时间或日期时间值的小时部分。

**例-1 :**
从指定日期和时间“2020-11-24 09:32:00”获取小时“9”。

```sql
SELECT HOUR("2020-11-24 09:32:00");

```

**输出:**

```sql
9
```

**示例-2 :**
从指定时间“06:12:23”获取小时“6”。

```sql
SELECT HOUR("06:12:23");

```

**输出:**

```sql
6
```

**例-3 :**
从指定时间“838:12:5”获取小时“838”。

```sql
SELECT HOUR("838:12:5");

```

**输出:**

```sql
838
```

**应用:**
此功能用于返回指定日期(从 0 到 838)的小时部分。