# MySQL 中的 DATEDIFF()函数

> 原文:[https://www.geeksforgeeks.org/datediff-function-in-mysql/](https://www.geeksforgeeks.org/datediff-function-in-mysql/)

[MySQL](https://www.geeksforgeeks.org/mysql-common-mysql-queries/) 中的 DATEDIFF()函数用于返回两个指定日期值之间的天数。

**语法:**

```sql
DATEDIFF(date1, date2)

```

**参数:**该函数接受如下给出的两个参数:

*   **Date 1:** The first specified date.
*   **Date 2:** The second specified date.

**返回:**

它返回两个指定日期值之间的天数。

**例 1 :**

获取两个指定日期值之间的天数，其中日期以 YYYY-MM-DD 格式指定。这里，日期 1 大于日期 2，因此返回值为正。

```sql
SELECT DATEDIFF("2020-11-20", "2020-11-1");  

```

**输出:**

```sql
19

```

**例 2:**

获取两个指定日期值之间的天数，其中日期以 YYYY-MM-DD 格式指定。这里，日期 1 小于日期 2，因此返回值为负。

```sql
SELECT DATEDIFF("2020-11-12", "2020-11-19");  

```

**输出:**

```sql
-7

```

**例 3:**

获取两个指定日期值之间的天数，其中日期以 YYYY-MM-DD HH-MM-SS 格式指定。

```sql
SELECT DATEDIFF("2020-11-20 09:34:21", "2020-11-17 09:34:21");  

```

**输出:**

```sql
3

```

**例 4:**

获取两个指定日期值之间的天数，其中日期以 YYYY-MM-DD HH-MM-SS 格式指定。这里，时间值无关紧要，因为日期 1 和日期 2 是相同的，但时间不同，输出仍然为零(0)。

```sql
SELECT DATEDIFF("2020-11-20 09:34:21", "2020-11-20 08:11:23");  

```

**输出:**

```sql
0

```