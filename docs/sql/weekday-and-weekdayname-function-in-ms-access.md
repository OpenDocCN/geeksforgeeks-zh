# MS Access 中的 Weekday()和 WeekdayName()函数

> 原文:[https://www . geesforgeks . org/weekday-weekday-name-function-in-ms-access/](https://www.geeksforgeeks.org/weekday-and-weekdayname-function-in-ms-access/)

**1。Weekday()函数:**
在 MS Access 中，weekday()函数返回给定日期的工作日数。在此函数中，日期将作为参数传递，并返回该日期的工作日。默认情况下，1 表示星期日，7 表示星期六。第二个参数是可选的，它将是一周的第一天。

**语法:**

```sql
Weekday(date, firstdayofweek)

```

**参数值:**

| 参数 | 描述 |
| 日期 | 这是必需的。有效日期。 |
| 第一天 | 可选，它将指定一周的第一天
**0 :** 对于 NLS API 设置
**1 :** 周日(默认)
**2 :** 周一
**3 :** 周二
**4 :** 周三
**5 :** 周四
**6 :** 周五
**7 :** 周六 |

**示例-1 :**

```sql
SELECT Weekday(#06/17/2020#);

```

**输出:**

```sql
4

```

**示例-2 :**

```sql
SELECT Weekday(Date());

```

**输出:**

```sql
5

```

**2。WeekdayName()函数:**
在 MS Access 中，WeekdayName()函数返回工作日名称。在这个函数中，第一个函数是周数，第二个参数是缩写，它是可选的。如果您想要缩写，则传递 true，否则传递 false。第三个参数是一周的第一天。它也是可选的。

**语法:**

```sql
WeekdayName(number, abbreviate, firstdayofweek)

```

**参数:**

| 参数 | 描述 |
| 数字 | 这是必需的。它将在 1 到 7 的范围内 |
| 缩写 | 可选。如果缩写为 true，则为 false |
| 第一天 | 可选，它将指定一周的第一天
**0 :** 对于 NLS API 设置
**1 :** 周日(默认)
**2 :** 周一
**3 :** 周二
**4 :** 周三
**5 :** 周四
**6 :** 周五
**7 :** 周六 |

**示例-1 :**

```sql
SELECT WeekdayName(1);

```

**输出:**

```sql
Sunday

```

**示例-2 :**

```sql
SELECT WeekdayName (3, TRUE, 2)

```

**输出:**

```sql
Wed

```