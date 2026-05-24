# MS Access 中的 `DateDiff()` 和 `DatePart()` 功能

> 原文: [https://www.geeksforgeeks.org/datediff-and-datepart-function-in-ms-access/](https://www.geeksforgeeks.org/datediff-and-datepart-function-in-ms-access/)

在本文中，我们将通过示例介绍 `DateDiff()` 和 `DatePart` 函数。`DateDiff()` 用于计算两个日期之间的差异。当您希望特定部分以日期指定的格式显示时，使用 `DatePart`。我们一个一个来讨论。

## 1. `DateDiff()` 函数

在 MS Access 中，`DateDiff()` 函数返回两个日期的差值。在这个函数中，它将采用第一个参数 `datepart`，第二个参数是 `date1`，第三个参数是 `date2`。它将返回两个日期之间的差异。

**语法:**

```sql
DateDiff(datepart, date1, date2, firstdayofweek, firstweekofyear)
```

**参数值:**

| 参数 | 说明 |
| :--- | :--- |
| `datepart` | 为必填项。要返回的部分。<br>`yyyy` = 年<br>`q` = 季度<br>`m` = 月<br>`y` = 一年中的某一天<br>`d` = 日<br>`w` = 工作日<br>`ww` = 周<br>`h` = 小时<br>`n` = 分钟<br>`s` = 秒 |
| `date1` 和 `date2` | 这是必填项。计算 `date2` 和 `date1` 之间差异的两个日期。 |
| `firstdayofweek` | 它是可选的。它将指定一周的第一天。<br>`0` = 使用 NLS API 设置<br>`1` = 周日 (这是默认设置)<br>`2` = 周一<br>`3` = 周二<br>`4` = 周三<br>`5` = 周四<br>`6` = 周五<br>`7` = 周六 |
| `firstweekofyear` | 这是可选的。它将指定一年的第一周。<br>`0` = 使用 NLS API 设置<br>`1` = 它表示包含 1 月 1 日的第一周 (默认情况下)<br>`2` = 它表示一年中的第一周。(至少 4 天)<br>`3` = 它使用一年中的第一个整周。 |

**示例-1:**

```sql
SELECT DateDiff("yyyy", #15/02/2000#, #06/05/2020#);
```

**输出:**

```sql

```

**示例-2:**

```sql
SELECT DateDiff("m", #15/02/2000#, #06/05/2020#);
```

**输出:**

```sql

```

## 2. `DatePart()` 函数

在 MS Access 中，`DatePart()` 函数返回日期的指定部分。在这个函数中，第一个参数是指定的日期部分符号，第二个参数是日期。它将返回日期的日期部分。

**语法:**

```sql
DatePart(datepart, date, firstdayofweek, firstweekofyear);
```

**参数值:**
在该参数中，`datepart`、`firstdayofweek` 和 `firstweekofyear` 的值与 `DateDiff()` 函数相同。对于 `date` 值，需要指定日期。

**示例-1:**

```sql
SELECT DatePart("yyyy", #02/09/2020#);
```

**输出:**

```sql

```

**示例-2:**

```sql
SELECT DatePart("m", #02/09/2020#);
```

**输出:**

```sql

```