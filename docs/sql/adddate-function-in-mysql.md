# MySQL 中的 ADDDATE()函数

> 原文:[https://www.geeksforgeeks.org/adddate-function-in-mysql/](https://www.geeksforgeeks.org/adddate-function-in-mysql/)

**ADDDATE()** 函数在 MySQL 中用来给给定的日期和时间加上指定的时间间隔。它返回添加间隔后的日期或日期时间。

**语法:**

```sql
ADDDATE(date, INTERVAL expr unit)
           OR
ADDDATE(expr, days)

```

**参数:**该方法接受两个参数。

*   **日期**:我们要修改的给定日期。
*   **天**:我们要添加到给定日期的天数。
*   **表达式:**日期或日期时间表达式或数字。它可以按照以下格式给出–

*   微秒
*   秒
*   分钟
*   小时
*   天
*   周；星期
*   月份
*   四分之一
*   年
*   秒。'微秒'
*   分钟:秒。'微秒'
*   分钟:秒
*   小时:分钟:秒。'微秒'
*   “小时:分钟:秒”
*   小时:分钟
*   天数小时:分钟:秒。'微秒'
*   '天小时:分钟:秒'
*   '天小时:分钟'
*   天数小时数
*   年-月

*   **单位:**要添加的区间类型。它是给定类型之一–
    *   微秒
    *   第二
    *   分钟
    *   小时
    *   天
    *   周
    *   月
    *   四分之一
    *   年
    *   秒 _ 微秒
    *   MINUTE _ 微秒
    *   分钟 _ 秒
    *   小时 _ 微秒
    *   小时 _ 秒
    *   小时 _ 分钟
    *   DAY _ 微秒
    *   第二天
    *   日 _ 分钟
    *   日 _ 小时
    *   年 _ 月

**返回:**返回添加间隔后的日期或日期时间。

**示例-1 :**
使用 ADDDATE 函数将 15 天与指定日期相加。

```sql
SELECT ADDDATE('2020-08-20', INTERVAL 15 DAY) 
as Updated_date;

```

**输出:**

| 更新日期 |
| --- |
| 2020-09-04 |

**示例-2 :**
使用 ADDDATE 函数用指定的日期时间添加 30 分钟。

```sql
SELECT ADDDATE('2020-08-28 20:59:59', INTERVAL 30 MINUTE) 
as Updated_datetime;

```

**输出:**

| 更新日期时间 |
| --- |
| 2020-08-28 21:29:59 |

**示例-3 :**
使用 ADDDATE 函数添加指定日期的 4 周。

```sql
SELECT ADDDATE('2020-08-12', INTERVAL 4 WEEK) 
as Updated_date;

```

**输出:**

| 更新日期 |
| --- |
| 2020-09-09 |

**示例-4 :**
使用 ADDDATE 函数添加指定日期的 6 个月。

```sql
SELECT ADDDATE('2019-08-12', INTERVAL 6 MONTH) 
as Updated_date ;

```

**输出:**

| 更新日期 |
| --- |
| 2020-02-12 |

**示例-5 :**
使用 ADDDATE 函数将指定日期加上 10 年。

```sql
SELECT ADDDATE('2010-12-10', INTERVAL 10 YEAR) 
as Updated_date ;

```

**输出:**

| 更新日期 |
| --- |
| 2020-12-10 |

**示例-6 :**
使用 ADDDATE 函数用指定的日期时间添加 5 天 10 小时 05 分 20 秒。

```sql
SELECT ADDDATE('2020-08-20 05:15:19', INTERVAL '5-10-05-20' DAY_SECOND) 
as Updated_datetime;

```

**输出:**

| 更新日期时间 |
| --- |
| 2020-08-25 15:20:39 |

**示例-7:**
ADDDATE 函数可用于设置列的值。为了演示，创建一个名为 ScheduleDetails 的表。

```sql
CREATE TABLE ScheduleDetails(
TrainId INT NOT NULL,
StationName VARCHAR(20) NOT NULL,
TrainName VARCHAR(20) NOT NULL,
ScheduledlArrivalTime DATETIME NOT NULL,
PRIMARY KEY(TrainId )
);
```

现在在 ScheduleDetails 表中插入值。我们将使用 ADDDATE 函数来表示到达时间的延迟。ExpectedArrivalTime 列中的值将是 ADDDATE 函数给出的值。

```sql
INSERT INTO  
ScheduleDetails (TrainId, StationName, TrainName, ScheduledlArrivalTime )
VALUES
(12859, 'KGP', 'Gitanjali Express ', '2020-11-17 10:20:10');
```

现在，检查调度详细信息表:

```sql
SELECT *, ADDDATE(ScheduledlArrivalTime, INTERVAL '0-5-05-20' DAY_SECOND)  
AS ExpectedArrivalTime FROM ScheduleDetails;

```

**输出:**

| 训练有素 | 车站名称 | 列车名称 | scheduledarrivaltiume | 期望的 |
| --- | --- | --- | --- | --- |
| Twelve thousand eight hundred and fifty-nine | KGP | 吉檀迦利快递 | 2020-11-17 10:20:10 | 2020-11-17 15:25:30 |