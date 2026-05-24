# 获取昨天和明天的 SQL 查询

> 原文:[https://www . geesforgeks . org/SQL-query-get-昨天和明天/](https://www.geeksforgeeks.org/sql-query-to-get-yesterday-and-tomorrow/)

查询帮助用户与数据库交互，以便使用不同的查询在数据库中创建、插入、删除和更新数据。

在本文中，让我们看看如何根据数据库中给定的日期获取昨天和明天。

示例–

给定日期:2021-03-23
昨天:2021-03-22 星期一
明天:2021-03-24 星期三

**创建数据库日历:**

```sql
CREATE DATABASE calendar;
```

![](img/cc5ee7f0a3a26064d82a4eeaa8439363.png)

**使用数据库日历**

```sql
USE calendar;
```

![](img/a7ef031e4ca0b453a7908d592ac545f6.png)

**创建表格时间表:**

```sql
CREATE TABLE schedule
(dates date);
```

![](img/a3f2c2e7311d2170f2e77ef6eab79883.png)

**查看表格描述:**

```sql
DESCRIBE schedule;
```

![](img/8ba09c8b10ade95d11f87db305f0984c.png)

**在计划中插入行:**

```sql
INSERT INTO schedule VALUES('2021-03-23');
INSERT INTO schedule VALUES('2020-08-04');
INSERT INTO schedule VALUES('2021-06-08');
INSERT INTO schedule VALUES('2030-04-04');
INSERT INTO schedule VALUES('2025-09-13');

```

![](img/1501fb2f72267eebcf37520221b659a8.png)

**查看表中数据:**

```sql
SELECT* FROMschedule;
```

![](img/5e8580f39ae3d56a7edc144733e5219c.png)

**查询得到当前日期的昨天和明天:**

为了得到当前日期的昨天和明天，我们可以使用 MySQL 中的 CURRDATE()函数，从中减去 1 得到昨天，再加上 1 得到明天。

```sql
SELECT CURDATE(),
    DATE_SUB(CURDATE(),INTERVAL 1 DAY) AS yesterday,
    DATE_ADD(CURDATE(),INTERVAL 1 DAY) AS tomorrow;
```

在这里，我们可以使用 AS 将默认的列标题更改为其他名称。

![](img/c476ce58c25dd5c81413f5e7e60f579f.png)

**示例 1:**

查询以获取表中日期的昨天和明天:

> **语法:**
> 选择日期 _ 子(日期)、
> 日期 _ 子(日期)、【间隔 1 天】作为某名称
> 日期 _ 添加(日期)、【间隔 1 天】作为某名称；

```sql
 SELECT dates,
     DATE_SUB(dates,INTERVAL 1 DAY) AS yesterday,
     DATE_ADD(dates,INTERVAL 1 DAY) AS tomorrow
     FROM schedule;
```

![](img/ecb296c2966fc156dd8c5a580f693335.png)

**示例 2:**

查询以获取工作日表中的昨天和明天日期:

> **语法:**
> 
> SELECT column_name，
> DATE_SUB(column_name，INTERVAL 1 DAY) AS some_name，
> DATE_ADD(column_name，INTERVAL 1 DAY) AS some_name，
> DAYNAME(当前 _ DATE)
> DAY name(前 _ 日)
> DAYNAME(下 _ 日)；

```sql
  SELECT dates,
     DATE_SUB(dates,INTERVAL 1 DAY) AS yesterday,
     DATE_ADD(dates,INTERVAL 1 DAY) AS tomorrow,
     DAYNAME(dates) AS weekdayofdate,
     DAYNAME(DATE_SUB(dates,INTERVAL 1 DAY)) AS weekdayofYd,
     DAYNAME( DATE_ADD(dates,INTERVAL 1 DAY)) AS weekdayofTm
     FROM schedule;
```

![](img/7ea45b5a92c9f91a6bd98056a7c8d4cf.png)