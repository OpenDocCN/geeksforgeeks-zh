# 是 PostgreSQL

中的 inite()、alignment _ days()和 alignment _ hours()函数

> 原文:[https://www . geesforgeks . org/is inite-justice _ days-and-justice _ hours-function-in-PostgreSQL/](https://www.geeksforgeeks.org/isfinite-justify_days-and-justify_hours-function-in-postgresql/)

**先决条件:**[PostgreSQL–简介](https://www.geeksforgeeks.org/what-is-postgresql-introduction/)

**1。PostgreSQL 中的 IsFinite()函数:**
PostgreSQL 中的这个函数有助于测试有限的日期、时间戳和时间间隔。因为我们知道 Postgre 支持具有无穷大或负无穷大值的时间戳，所以这里 IsFinite()函数起着重要的作用。该函数将测试给定的数据或时间戳，并相应地返回真或假。

**语法–**

```sql
isfinite(date)
isfinite(timestamp)
isfinite(interval)
```

**参数–**
该函数只接受一个参数，可以是以下参数之一–

*   日期
*   时间戳
*   间隔

**返回–**
如果给定的日期/时间戳/间隔是有限的，函数将返回“真”或“t”，否则返回“假”或“f”。

**例 1–**
使用日期“2021-09-13”检查 IsFinite()函数的工作情况

```sql
SELECT isfinite(date '2021-09-13');
```

**输出–**True
由于日期“2021-09-13”不是无限的，所以函数会返回 True。

**例 2–**
使用时间戳“2021-09-13 12:15:05”检查 IsFinite()函数的工作情况

```sql
SELECT isfinite(timestamp '2021-09-13 12:15:05');
```

**输出–**True
由于时间戳“2021-09-13 12:15:05”不是无穷大，所以函数将返回 True。

**示例 3–**
使用间隔“5 小时 15 分钟”检查 IsFinite()功能的工作情况

```sql
SELECT isfinite(interval '5 hours 15 minutes');
```

**输出–**真
由于间隔“5 小时 15 分钟”不是无限的，所以函数将返回真。

**示例 4–**
使用“无穷大”常数检查 IsFinite()函数的工作情况

```sql
SELECT isfinite('infinity'::timestamp);
```

**输出–**False
由于无限常数作为参数传递，因此函数将返回 False。

**示例 5–**
使用“-infinite”(负无穷大)常数检查 IsFinite()函数的工作情况

```sql
SELECT isfinite('-infinity'::timestamp);
```

**输出–**False
由于-无限常数作为参数传递，因此函数将返回 False。

**2。PostgreSQL 中的狡辩 _days()** **函数:**
PostgreSQL 中的该函数有助于调整间隔值，即该函数可以将 30 天的时间段表示为月份。就像如果用户传递 30 天作为参数，函数将返回 1 mon，以此类推。

**语法–**

```sql
justify_days(interval)
```

**参数–**
该函数只接受一个参数

*   **区间–**
    某一区间即可以表示月份
*   **返回–**
    该函数将以月为单位转换并返回给定的时间间隔。

**示例 1–**
使用间隔“90 天”检查的工作情况

```sql
SELECT justify_days(interval '90 days');
```

**输出–**3 日
由于 30 天等于 1 个月，因此 90 天将表示为 3 个月。

**例 2–**
当间隔不是 30 的完美倍数
时，检查狡辩 _days ()功能的工作情况，以间隔为 35 天。

```sql
SELECT justify_days(interval '35 days');
```

**输出–**1 周一 5 天
由于间隔不是 30 的完美倍数，所以结果将以月和日的形式出现。

**示例 3–**
当间隔小于 30 天时，检查调整 _ 天()功能的工作情况

```sql
SELECT justify_days(interval '14 days');
```

**产量–**14 天
由于给定的间隔是 14 天，小于 30 天，所以产量将保持 14 天。

**示例 4–**
检查的工作情况证明 _ 天()功能当时间也随着流逝时间隔
1。以 50 天 40 分钟为间隔。

```sql
SELECT justify_days(interval '50 days 40 minutes');
```

**输出–**1 周一 20 天 00:40:00

2。以 160 天 2 小时 40 分 59 秒为间隔。

```sql
SELECT justify_days(interval '160 days 2 hours 40 minutes 59 seconds');
```

**输出–**5 周一 10 天 02:40:59
由于时间也是以时间间隔传递的，因此输出以 HH:MM:SS 格式显示月、日和时间。

**3。** **函数:**
PostgreSQL 中的这个函数有助于调整间隔值，即该函数可以将 24 小时时间段表示为天。就像如果用户通过 24 小时作为参数，函数将返回 1 天，以此类推。

**语法–**

```sql
justify_hours(interval)
```

**参数–**
该函数只接受一个参数，

*   **间隔–**
    某一间隔即可以表示的天数
*   **返回–**
    该函数将以天为单位转换并返回给定的时间间隔。

**示例 1–**
使用间隔“72 小时”检查的工作情况

```sql
SELECT justify_hours(interval '72 hours');
```

**输出–**3 天
由于 24 小时等于 1 天，因此 72 小时将表示为 3 天。

**示例 2–**
当间隔小于 24 小时时，检查调整 _ 小时()功能的工作

```sql
SELECT justify_hours(interval '14 hours');
```

**输出–**14:00:00
由于给定的时间间隔为 14 小时，小于 24 小时，因此输出将为 HH:MM:SS 格式。

**示例 3–**
当间隔处于形式时，检查调整 _ 小时()功能的工作情况。
1。以 5.53 个月为间隔。

```sql
SELECT justify_hours(interval '5.53 months');
```

**输出–**5 周一 15 天 21:36:00

2。以间隔为 300 小时 58 分钟。

```sql
SELECT justify_hours(interval '300 hours 58 minutes');
```

**输出–**12 天 12:58:00

3。以间隔为 3000 小时 10 分 20 秒。

```sql
SELECT justify_hours(interval '3000 hours 10 minutes 20 seconds');
```

**输出–**125 天 00:10:20
输出将以月、日和时间显示，格式为 HH:MM:SS。