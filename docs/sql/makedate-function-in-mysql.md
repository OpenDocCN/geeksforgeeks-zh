# MySQL 中的 MAKEDATE()函数

> 原文:[https://www.geeksforgeeks.org/makedate-function-in-mysql/](https://www.geeksforgeeks.org/makedate-function-in-mysql/)

**MAKEDATE():**
MySQL 中的这个函数用于根据一年和天数值创建并返回一个日期。天数必须大于 0，否则将返回空值。

**语法:**

```sql
MAKEDATE(year, day)
```

**参数:**

该函数接受两个参数，如下所示。

*   **年份–**表示我们要创建的年份。
*   **day–**表示我们想要创建的一年中的天数。

**返回:**

它根据一年和一天的数值返回一个日期。

**示例-1 :**

基于年和天数值创建和返回日期。这里日期取 2020 年，天数 31。所以，MAKEDATE 函数将返回日期 31-01-2020。

```sql
SELECT MAKEDATE(2020,31) AS NEWDATE ;
```

**输出:**

| 新约会 |
| --- |
| 2020-01-31 |

**示例-2 :**

基于年和天数值创建和返回日期。这里的日期是 2020 年，日数小于 0。因此，MAKEDATE 函数将返回空值。

```sql
SELECT MAKEDATE(2020,-1) AS NEWDATE ;
```

**输出:**

| 新约会 |
| --- |
| 空 |

**示例-3 :**

基于年和天数值创建和返回日期。这里的日期是 2020 年，日数是 366。因此，MAKEDATE 函数将返回一年中的最后一天，因为它是闰年。

```sql
SELECT MAKEDATE(2020,366) AS NEWDATE ;
```

**输出:**

| 新约会 |
| --- |
|  2020-12-31 |

**示例-4 :**

基于年和天数值创建和返回日期。这里日期取 2015 年，日号 366。因此，MAKEDATE 函数将返回第二年的第一天，即 2016 年 1 月 1 日。

```sql
SELECT MAKEDATE(2015,366) AS NEWDATE ;
```

**输出:**

| 新约会 |
| --- |
| 2016-01-01 |