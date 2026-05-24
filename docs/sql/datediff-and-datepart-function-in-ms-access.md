# MS Access 中的 DateDiff()和 DatePart()功能

> 原文:[https://www . geesforgeks . org/datediff-and-datepart-function in-ms-access/](https://www.geeksforgeeks.org/datediff-and-datepart-function-in-ms-access/)

在本文中，我们将通过示例介绍 DateDiff()和 DatePart 函数。DateDiff()用于计算两个日期之间的差异。当您希望特定部分以日期指定的格式显示时，使用 DatePart。我们一个一个来讨论。

**1。DateDiff()函数:**
在 MS Access 中，DateDiff()函数返回两个日期的差值。在这个函数中，它将采用第一个参数 datepart，第二个参数是 date1，第三个参数是 date2。它将返回两个日期之间的差异。

**语法:**

```sql
DateDiff(datepart, date1, date2, firstdayofweek, firstweekofyear)

```

**参数值:**

| 参数 | **说明** |
| [日期部分](https://www.geeksforgeeks.org/sql-date-functions/) | 为必填项。要返回的部分。
yyyy =年
q =季度
m =月
y =一年中的某一天
d =日
w =工作日
ww =周
h =小时
n =分钟
s =秒 |
| T21】日期 1 和日期 2 | 这是必填项。计算日期 2 和日期 1 之间差异的两个日期。 |
| [first day fweek](https://www.geeksforgeeks.org/find-day-of-the-week-for-a-given-date/) | 它是可选的。它将指定一周的第一天。
0 =使用 NLS API 设置
1 =周日(这是默认设置)
2 =周一
3 =周二
4 =周三
5 =周四
6 =周五
7 =周六 |
| [第一天](https://www.geeksforgeeks.org/month-firstdayofyear-method-in-java/) | 这是可选的。它将指定一年的第一周。
0 =使用 NLS 空气污染指数设置
1 =它表示包含 1 月 1 日的第一周(默认情况下)
2 =它表示一年中的第一周。(至少 4 天)
3 =它使用一年中的第一个整周。 |

**示例-1 :**

```sql
SELECT DateDiff("yyyy", #15/02/2000#, #06/05/2020#);

```

**输出:**

```sql
20

```

**示例-2 :**

```sql
SELECT DateDiff("m", #15/02/2000#, #06/05/2020#);

```

**输出:**

```sql
244

```

**2。DatePart()函数:**
在 MS Access 中，DatePart()函数返回日期的指定部分。在这个函数中，第一个参数是指定的日期部分符号，第二个参数是日期。它将返回日期的日期部分。

**语法:**

```sql
DatePart(datepart, date, firstdayofweek, firstweekofyear);

```

**参数值:**
在该参数中，datepart、firstdayofweek 和 firstdayofweek 的值与 Datadiff()函数相同。对于数据值，需要指定日期。

**示例-1 :**

```sql
SELECT DatePart("yyyy", #02/09/2020#);

```

**输出:**

```sql
2020

```

**示例-2 :**

```sql
SELECT DatePart("m", #02/09/2020#);

```

**输出:**

```sql
2

```