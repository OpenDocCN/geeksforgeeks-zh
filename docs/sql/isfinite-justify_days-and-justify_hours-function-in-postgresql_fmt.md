# PostgreSQL 中的 `isfinite()`、`justify_days()` 和 `justify_hours()` 函数

> 原文: [https://www.geeksforgeeks.org/isfinite-justify_days-and-justify_hours-function-in-postgresql/](https://www.geeksforgeeks.org/isfinite-justify_days-and-justify_hours-function-in-postgresql/)

**先决条件:** [PostgreSQL–简介](https://www.geeksforgeeks.org/what-is-postgresql-introduction/)

## 1. PostgreSQL 中的 `isfinite()` 函数

PostgreSQL 中的这个函数有助于测试有限的日期、时间戳和时间间隔。因为我们知道 PostgreSQL 支持具有无穷大或负无穷大值的时间戳，所以这里 `isfinite()` 函数起着重要的作用。该函数将测试给定的数据或时间戳，并相应地返回真或假。

**语法**

```sql
isfinite(date)
isfinite(timestamp)
isfinite(interval)
```

**参数**

该函数只接受一个参数，可以是以下参数之一：

*   `date`
*   `timestamp`
*   `interval`

**返回**

如果给定的日期/时间戳/间隔是有限的，函数将返回 `true` 或 `t`，否则返回 `false` 或 `f`。

**示例 1**

使用日期 `'2021-09-13'` 检查 `isfinite()` 函数的工作情况。

```sql
SELECT isfinite(date '2021-09-13');
```

**输出**

```
true
```

由于日期 `'2021-09-13'` 不是无限的，所以函数会返回 `true`。

**示例 2**

使用时间戳 `'2021-09-13 12:15:05'` 检查 `isfinite()` 函数的工作情况。

```sql
SELECT isfinite(timestamp '2021-09-13 12:15:05');
```

**输出**

```
true
```

由于时间戳 `'2021-09-13 12:15:05'` 不是无穷大，所以函数将返回 `true`。

**示例 3**

使用间隔 `'5 hours 15 minutes'` 检查 `isfinite()` 函数的工作情况。

```sql
SELECT isfinite(interval '5 hours 15 minutes');
```

**输出**

```
true
```

由于间隔 `'5 hours 15 minutes'` 不是无限的，所以函数将返回 `true`。

**示例 4**

使用 `'infinity'` 常数检查 `isfinite()` 函数的工作情况。

```sql
SELECT isfinite('infinity'::timestamp);
```

**输出**

```
false
```

由于无限常数作为参数传递，因此函数将返回 `false`。

**示例 5**

使用 `'-infinity'`（负无穷大）常数检查 `isfinite()` 函数的工作情况。

```sql
SELECT isfinite('-infinity'::timestamp);
```

**输出**

```
false
```

由于 `-infinity` 常数作为参数传递，因此函数将返回 `false`。

## 2. PostgreSQL 中的 `justify_days()` 函数

PostgreSQL 中的该函数有助于调整间隔值，即该函数可以将 30 天的时间段表示为月份。就像如果用户传递 30 天作为参数，函数将返回 `1 mon`，以此类推。

**语法**

```sql
justify_days(interval)
```

**参数**

该函数只接受一个参数：

*   `interval` – 某一间隔，即可以表示月份。

**返回**

该函数将以月为单位转换并返回给定的时间间隔。

**示例 1**

使用间隔 `'90 days'` 检查 `justify_days()` 的工作情况。

```sql
SELECT justify_days(interval '90 days');
```

**输出**

```
3 mons
```

由于 30 天等于 1 个月，因此 90 天将表示为 3 个月。

**示例 2**

当间隔不是 30 的完美倍数时，检查 `justify_days()` 函数的工作情况，以间隔为 35 天。

```sql
SELECT justify_days(interval '35 days');
```

**输出**

```
1 mon 5 days
```

由于间隔不是 30 的完美倍数，所以结果将以月和日的形式出现。

**示例 3**

当间隔小于 30 天时，检查 `justify_days()` 函数的工作情况。

```sql
SELECT justify_days(interval '14 days');
```

**输出**

```
14 days
```

由于给定的间隔是 14 天，小于 30 天，所以输出将保持 14 天。

**示例 4**

检查 `justify_days()` 函数当时间也随着间隔传递时的工作情况。

1.  以 50 天 40 分钟为间隔。

```sql
SELECT justify_days(interval '50 days 40 minutes');
```

**输出**

```
1 mon 20 days 00:40:00
```

2.  以 160 天 2 小时 40 分 59 秒为间隔。

```sql
SELECT justify_days(interval '160 days 2 hours 40 minutes 59 seconds');
```

**输出**

```
5 mons 10 days 02:40:59
```

由于时间也是以时间间隔传递的，因此输出以 `HH:MM:SS` 格式显示月、日和时间。

## 3. PostgreSQL 中的 `justify_hours()` 函数

PostgreSQL 中的这个函数有助于调整间隔值，即该函数可以将 24 小时时间段表示为天。就像如果用户通过 24 小时作为参数，函数将返回 1 天，以此类推。

**语法**

```sql
justify_hours(interval)
```

**参数**

该函数只接受一个参数：

*   `interval` – 某一间隔，即可以表示的天数。

**返回**

该函数将以天为单位转换并返回给定的时间间隔。

**示例 1**

使用间隔 `'72 hours'` 检查 `justify_hours()` 的工作情况。

```sql
SELECT justify_hours(interval '72 hours');
```

**输出**

```
3 days
```

由于 24 小时等于 1 天，因此 72 小时将表示为 3 天。

**示例 2**

当间隔小于 24 小时时，检查 `justify_hours()` 函数的工作情况。

```sql
SELECT justify_hours(interval '14 hours');
```

**输出**

```
14:00:00
```

由于给定的时间间隔为 14 小时，小于 24 小时，因此输出将为 `HH:MM:SS` 格式。

**示例 3**

当间隔处于不同形式时，检查 `justify_hours()` 函数的工作情况。

1.  以 5.53 个月为间隔。

```sql
SELECT justify_hours(interval '5.53 months');
```

**输出**

```
5 mons 15 days 21:36:00
```

2.  以间隔为 300 小时 58 分钟。

```sql
SELECT justify_hours(interval '300 hours 58 minutes');
```

**输出**

```
12 days 12:58:00
```

3.  以间隔为 3000 小时 10 分 20 秒。

```sql
SELECT justify_hours(interval '3000 hours 10 minutes 20 seconds');
```

**输出**

```
125 days 00:10:20
```

输出将以月、日和时间显示，格式为 `HH:MM:SS`。