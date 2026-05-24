# MySQL 中的 ADDTIME()函数

> 原文:[https://www.geeksforgeeks.org/addtime-function-in-mysql/](https://www.geeksforgeeks.org/addtime-function-in-mysql/)

**MySQL 中的 ADDTIME()** 函数用于将指定的时间间隔添加到给定的日期和时间。它在添加时间间隔后返回日期或日期时间。

**语法:**

```sql
ADDTIME(expr1, expr2)

```

**参数:**该方法接受两个参数。

*   **表达式 1 :** 我们要修改的给定日期时间或时间。
*   **表达式 2 :** 我们要添加到给定日期时间的时间间隔。它可以是积极的，也可以是消极的。

**返回:**返回给定时间间隔相加后的日期或日期时间。

**示例-1 :**
使用 ADDTIME 函数将指定时间加上 15 秒。

```sql
SELECT ADDTIME("11:34:21", "15") as Updated_time ;

```

**输出:**

| 更新时间 |
| --- |
| 11:34:36 |

**示例-2 :**
使用 ADDTIME 函数将指定时间加上 10 分钟。

```sql
SELECT ADDTIME("10:54:21", "00:10:00") 
as Updated_time ;

```

**输出:**

| 更新时间 |
| --- |
| 11:04:21 |

**示例-3 :**
使用 ADDTIME 函数用指定的日期时间添加 12 个小时。

```sql
SELECT ADDTIME("2009-02-20 18:04:22.333444", "12:00:00") 
as Updated_time ;

```

**输出:**

| 更新时间 |
| --- |
|  2009-02-21 06:04:22.333444 |

**示例-4 :**
使用 ADDTIME 函数将 10 小时 30 分 25 秒和 100000 微秒与指定的日期时间相加。

```sql
SELECT ADDTIME("2020-09-20 17:04:22.222333", "10:30:25.100000") 
as Updated_time ;

```

**输出:**

| 更新时间 |
| --- |
| 2020-09-21 03:34:47.322333 |

**示例-5:**
ADDTIME 函数可用于设置列的值。为了演示如何创建一个名为 ScheduleDetails 的表

```sql
CREATE TABLE ScheduleDetails(
TrainId INT NOT NULL,
StationName VARCHAR(20) NOT NULL,
TrainName VARCHAR(20) NOT NULL,
ScheduledlArrivalTime TIME NOT NULL,
PRIMARY KEY(TrainId )
);
```

现在在 ScheduleDetails 表中插入值。我们将使用 ADDTIME 函数来表示到达时间的延迟。ExpectedArrivalTime 列中的值将是 ADDTIME 函数给出的值。

```sql
INSERT INTO  
ScheduleDetails (TrainId, StationName, TrainName, ScheduledlArrivalTime )
VALUES
(12345, 'NJP', 'Saraighat Express', "17:04:22");

```

现在，检查调度详细信息表:

```sql
SELECT *, ADDTIME(ScheduledlArrivalTime, "00:10:00") 
AS ExpectedArrivalTime FROM ScheduleDetails;

```

**输出:**

| 训练有素 | 车站名称 | 列车名称 | scheduledlarrivaltiume | 期望的 |
| --- | --- | --- | --- | --- |
| one two three four five | 网络作业处理 | 萨拉伊加特快车 | 17:04:22 | 17:14:22 |