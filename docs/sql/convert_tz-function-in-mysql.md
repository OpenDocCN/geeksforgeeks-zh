# MySQL 中的 CONVERT_TZ()函数

> 原文:[https://www.geeksforgeeks.org/convert_tz-function-in-mysql/](https://www.geeksforgeeks.org/convert_tz-function-in-mysql/)

**CONVERT_TZ** ()函数在 MySQL 中用于将给定的 DateTime 从一个时区转换到另一个时区。如果参数无效，函数将返回空值。

**语法:**

```sql
CONVERT_TZ (dt, from_tz,to_tz) 
```

**参数:**该方法接受三参数。

*   **dt** :我们要转换的给定日期时间。
*   **from_tz** :我们要转换日期时间的时区。
*   **到 _tz** :我们要转换日期时间的时区。

**返回:**
转换为指定时区后返回日期时间。

**示例-1 :**

将日期时间从格林尼治标准时间转换为 IST 标准时间

```sql
SELECT CONVERT_TZ('2020-11-19 19:59:00', '+00:00', '+05:30') 
As IST_TIME;

```

**输出:**

| 是 _TIME |
| --- |
| 2020-11-20 01:29:00 |

**示例-2 :**

将日期时间从格林尼治标准时间转换为海湾标准时间

```sql
SELECT CONVERT_TZ('2020-11-19 10:53:00', '+00:00', '+04:00') 
As GST_TIME;

```

**输出:**

| gettime |
| --- |
|  2020-11-19 14:53:00 |

**示例-3 :**

CONVERT_TZ 函数可以用来设置列的值。为了演示，创建一个名为 FlightDetails 的表。

```sql
CREATE TABLE FlightDetails(
FlightId INT NOT NULL,
Source VARCHAR(20) NOT NULL,
Destination VARCHAR(20) NOT NULL,
DepartureTime DATETIME NOT NULL,
ArrivalTime DATETIME NOT NULL,
PRIMARY KEY(FlightId )
);

```

现在在 FlightDetails 表中插入值。我们将使用 CONVERT_TZ 功能来检查始发地和目的地机场的出发和到达时间。

```sql
INSERT INTO  
FlightDetails(FlightId, Source, Destination, 
              DepartureTime , ArrivalTime )
VALUES
(12345, 'New York', 'New Delhi', '2020-11-19 10:53:00',
                                 '2020-11-20 12:53:00');

```

现在，检查飞行细节

```sql
SELECT 
FlightId , Source ,Destination , 
DepartureTime  AS DepTimeInEST ,
CONVERT_TZ(DepartureTime, '-05:00', '+05:30') 
As DepTimeInIST ,

ArrivalTime  AS ArrTimeInIST ,
CONVERT_TZ(ArrivalTime , '+05:30', '-05:00') 
As ArrTimeInEST 
FROM FlightDetails;

```

**输出:**

| 高兴的 | 来源 | 目的地 | DEPTIMEINEST | DEPTIMEINIST | 坚持 | ARRTIMEINEST |
| --- | --- | --- | --- | --- | --- | --- |
| one two three four five | 纽约 | 新德里 |  2020-11-19 10:53:00  | 2020-11-19 21:23:00 | 2020-11-20 12:53:00 | 2020-11-20 02:23:00 |