# MySQL 中的 EXTRACT()函数

> 原文:[https://www.geeksforgeeks.org/extract-function-in-mysql/](https://www.geeksforgeeks.org/extract-function-in-mysql/)

**EXTRACT()功能:**

MySQL 中的这个函数用于从指定的日期提取一个零件。

**语法:**

```sql
EXTRACT(part FROM date)
```

**参数:**

该方法接受两个参数，如下图所示:

*   **Part–** Specify the part to be extracted, such as seconds, minutes, hours, days, weeks, months, years, etc.
*   **Date–** Select the specified date of the part.

**返回:**

它返回指定日期所需的提取部分。

**示例-1 :**

提取指定日期“2020-11-24”的周。

```sql
SELECT EXTRACT(WEEK FROM "2020-11-24");
```

**输出:**

```sql
47
```

**示例-2 :**

从指定日期和时间“2020-10-22 07:12:23”提取小时。

```sql
SELECT EXTRACT(HOUR FROM "2020-10-22 07:12:23");
```

**输出:**

```sql
7
```

**示例-3 :**

从指定的日期和时间“2020-10-22 07:12:23”中提取年和月。

```sql
SELECT EXTRACT(YEAR_MONTH FROM "2020-10-22 07:12:23");
```

**输出:**

```sql
202010
```