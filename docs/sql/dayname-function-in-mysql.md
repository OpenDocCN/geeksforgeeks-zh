# MySQL 中的 DAYNAME()函数

> 原文:[https://www.geeksforgeeks.org/dayname-function-in-mysql/](https://www.geeksforgeeks.org/dayname-function-in-mysql/)

**DAYNAME()函数:**
这个函数在 [MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中用来返回指定日期的工作日名称。

**语法:**

```sql
DAYNAME(date)

```

**参数:**
该方法接受如下所示的参数。

*   **日期–**提取工作日名称的指定日期

**返回:**
返回指定日期的工作日名称。

**示例-1 :**
获取指定日期的工作日名称。"2020-11-24".

```sql
SELECT DAYNAME("2020-11-24");  

```

**输出:**

```sql
Tuesday

```

**示例-2 :**
从指定日期“2020-11-22 07:12:23”获取工作日名称。

```sql
SELECT DAYNAME("2020-11-22 07:12:23");  

```

**输出:**

```sql
Sunday

```

**示例-3 :**
获取当前系统日期的工作日名称。

```sql
SELECT DAYNAME(CURDATE());

```

**输出:**

```sql
Tuesday

```

**应用:**
该函数用于返回指定日期的工作日名称。