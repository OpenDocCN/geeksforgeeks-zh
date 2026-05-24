# MySQL 中的 BIT_COUNT()函数

> 原文:[https://www.geeksforgeeks.org/bit_count-function-in-mysql/](https://www.geeksforgeeks.org/bit_count-function-in-mysql/)

**BIT_COUNT** ()函数在 MySQL 中用于返回给定输入中活动的位数。有效位可以计为二进制数中的 1。

**语法:**

```sql
BIT_COUNT(number)
```

**参数:**该方法只接受一个参数。

*   **数字–**
    输入我们要计算其有效位数的整数。

**返回:**返回数字中设置的有效位数。

**示例-1 :**
使用 BIT_COUNT 函数查找数字 0 的有效位数。由于给定输入的等效二进制数是 0，因此等效二进制数中的 1 也是 0。因此，这里我们将得到 0 个有效位。

```sql
SELECT BIT_COUNT(0) AS ActiveBits;
```

**输出:**

<figure class="table">

| 有效位 |
| --- |
| Zero |

</figure>

**示例-2 :**
使用 BIT_COUNT 函数查找数字 14 的有效位数。我们知道 14 的等价二进制表示是 1110。在这里我们可以看到 1 在场的人数是 3。所以，结果会是 3。

```sql
SELECT BIT_COUNT(14) AS ActiveBits;
```

**输出:**

<figure class="table">

| 有效位 |
| --- |
| three |

</figure>

**示例-3 :**
使用 BIT_COUNT 函数查找以下二进制数的有效位数。由于下例中 1 的个数分别为 0、1、4 和 7，因此我们将得到 0、1、4 和 7 个有效位。

```sql
SELECT BIT_COUNT(b'0000') AS ActiveBits1, 
BIT_COUNT(b'00100') AS ActiveBits2,
BIT_COUNT(b'01010101') AS ActiveBits3, 
BIT_COUNT(b'1111111') AS ActiveBits4;
```

**输出:**

<figure class="table">

| 活动位 S1 | 活动位 S2 | 活动位 S3 | 活动位 S4 |
| --- | --- | --- | --- |
| Zero | one | four | seven |

</figure>

**示例-4 :**
BIT_COUNT 函数也可以用于列数据。为了演示，创建一个名为 HolidayDetails 的表。

```sql
CREATE TABLE HolidayDetails (
Holiday_id INT AUTO_INCREMENT,  
YearDetails YEAR(4), 
MonthDetails INT(2) UNSIGNED ZEROFILL, 
DayDetails INT(2) UNSIGNED ZEROFILL,
PRIMARY KEY(Holiday_id));
```

将一些数据插入假期详细信息表–

```sql
INSERT INTO HolidayDetails
(YearDetails, MonthDetails, DayDetails) VALUES
(2021, 1, 1), (2021, 1, 14),
(2021, 1, 26), (2021, 2, 19), 
(2021, 2, 21), (2021, 3, 10);
```

因此，假期详情表如下–

```sql
SELECT * from HolidayDetails;
```

<figure class="table">

| 假日 _ 标识 | YEARDETAILS | 每月明细 | 日详细信息 |
| --- | --- | --- | --- |
| one | Two thousand and twenty-one | one | one |
| Two | Two thousand and twenty-one | one | Fourteen |
| three | Two thousand and twenty-one | one | Twenty-six |
| four | Two thousand and twenty-one | Two | Nineteen |
| five | Two thousand and twenty-one | Two | Twenty-one |
| six | Two thousand and twenty-one | three | Ten |

</figure>

现在，我们将找到每月的假期数–

```sql
SELECT YearDetails, MonthDetails, 
BIT_COUNT(BIT_OR(1<<DayDetails)) AS No_Of_Holidays 
FROM HolidayDetails 
GROUP By YearDetails, MonthDetails;
```

**输出:**

<figure class="table">T24】2021

| 年份详细信息 | 每月明细 | 无假日 |
| --- | --- | --- |
| Two thousand and twenty-one | 01 | three |
| 02 | Two |

</figure>