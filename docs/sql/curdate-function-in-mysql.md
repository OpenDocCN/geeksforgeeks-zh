# MySQL 中的 CODETATE()函数

> 原文:[https://www.geeksforgeeks.org/curdate-function-in-mysql/](https://www.geeksforgeeks.org/curdate-function-in-mysql/)

**CURDATE()函数:**
这个函数在 [MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中用来返回当前日期。日期以“YYYY-MM-DD”(字符串)或 YYYYMMDD(数字)的格式返回。该函数等于 CURRENT_DATE()函数。

**语法:**

```sql
CURDATE()

```

**参数:**

此方法不接受任何参数。

**返回:**

它返回当前日期。

**示例-1 :**

以“YYYY-MM-DD”(字符串)格式获取当前日期。

```sql
SELECT CURDATE();

```

**输出:**

```sql
2020-11-19

```

**示例-2 :**

以 YYYMMDD(数字)格式获取比当前日期晚 1 天的日期。

```sql
SELECT CURDATE() + 1;

```

**输出:**

```sql
20201120

```

**示例-3 :**

以 YYYMMDD(数字)格式获取当前日期前 5 天的日期。

```sql
SELECT CURDATE() + 5;

```

**输出:**

```sql
20201114

```

**应用:**

此函数用于以“YYYY-MM-DD”(字符串)或 YYYYMMDD(数字)两种不同格式获取当前日期或当前日期前后的指定天数。