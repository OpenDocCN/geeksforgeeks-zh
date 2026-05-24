# SQL 中的日期操作函数

> 原文：[https://www.geeksforgeeks.org/date-manipulating-functions-in-sql/](https://www.geeksforgeeks.org/date-manipulating-functions-in-sql/)

为了从表中操作和获取日期值，Oracle 内置了日期函数。这里，我们将介绍 SQL 中的日期操作函数。

## 1. `ADD_MONTHS`

它将把 `n` 中指定的月数加到 `date` 参数上并返回日期。

**语法**：

```sql
ADD_MONTHS(d, n)
```

**示例**：

```sql
Select ADD_MONTHS(SYSDATE, 4) "Add months" from dual;
```

**输出**：

```sql
Add Months
01-NOV-04
```

## 2. `LAST_DAY`

在 `LAST_DAY` 函数中，它将返回该月的最后一天。对于指定的月份，例如系统日期是 11 月 1 日，那么它将返回 11 月 30 日。

**语法**：

```sql
LAST_DAY(date)
```

**示例**：

```sql
Select SYSDATE, LAST_DAY(SYSDATE) "Last Day" from dual;
```

**输出**：

```sql
SYSDATE                Last Day
01-NOV-04             30-NOV-04
```

## 3. `MONTHS_BETWEEN`

返回 `date1` 和 `date2` 之间的月数。

**语法**：

```sql
MONTHS_BETWEEN(date1, date2)
```

**示例**：

```sql
Select MONTHS_BETWEEN('02-FEB-00', '01-JAN-00') "Months" from dual;
```

**输出**：

```sql
Months
```

## 4. `NEXT_DAY`

它将返回在 `date` 参数指定的日期之后的第一个工作日的日期。`char` 应指定为星期几。

**语法**：

```sql
NEXT_DAY(date, char)
```

**示例**：

```sql
SELECT NEXT_DAY('06-JUL-02', 'saturday') "Next day" from dual;
```

这里返回下周六的日期。

**输出**：

```sql
Next day
13-JUL-02
```

## 5. `NEW_TIME`

将日期从 `zone1` 时区转换为 `zone2` 时区的日期后返回。

**语法**：

```sql
NEW_TIME(date, zone1, zone2)
```

<figure class="table">

| **值** | **描述** | **值** | **描述** |
| --- | --- | --- | --- |
| 大西洋时间 | 大西洋时间 | 大西洋夏令时间 | 大西洋夏令时 |
| 牛生长激素 | 白令标准时间 | BDT | 白令夏令时 |
| 中央标准时间 | 中部标准时间 | 中央日光时间 | 中央采光时间 |
| GreenwichMeanTime 格林尼治标准时间 | 格林威治标准时间 | 期刊 | 纽芬兰标准时间 |
| HDT | 阿拉斯加-夏威夷夏令时 | 高速列车 | 阿拉斯加-夏威夷标准时间 |
| 山区夏令时 | 山区日光时间 | 山地时间 | 山区标准时间 |
| 悄悄话 | 太平洋标准时 | 太平洋夏季时间 | 太平洋夏令时 |

</figure>

**示例**：

```sql
Select NEW_TIME(To_date('2004/07/01 01:45', 'yyyy/mm/dd HH24:MI'), 
'AST', 'MST') "MST" from dual;
```

**输出**：

```sql
MST
30-JUN-04
```

这将大西洋标准时间转换为山区标准时间。