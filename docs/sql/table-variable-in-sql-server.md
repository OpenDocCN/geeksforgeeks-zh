# SQL Server 中的表变量

> 原文:[https://www.geeksforgeeks.org/table-variable-in-sql-server/](https://www.geeksforgeeks.org/table-variable-in-sql-server/)

**表变量**是一种用于临时存储数据的局部变量，类似于 SQL Server 中的[临时表。Tempdb 数据库用于存储表变量。](https://www.geeksforgeeks.org/sql-declare-local-temporary-table/)

若要声明表变量，请启动 declare 语句。表变量的名称必须以符号(@)开头。TABLE 关键字定义使用的变量是一个表变量。在 table 关键字之后，定义 SQL Server 中 TABLE 变量的列名和数据类型。

**语法:**

```sql
DECLARE @TABLEVARIABLE TABLE
(column1 datatype,  
column2 datatype,  
columnN datatype
)
```

**示例-1:**
DECLARE @ WeekDays TABLE(Number INT，Day VARCHAR(40)，Name VARCHAR(40))

```sql
INSERT INTO @WeekDays
VALUES

(1, 'Mon', 'Monday'),
(2, 'Tue', 'Tuesday'),
(3, 'Wed', 'Wednesday'),
(4, 'Thu', 'Thursday'),
(5, 'Fri', 'Friday'),
(6, 'Sat', 'Saturday'),
(7, 'Sun', 'Sunday')

```

**选择* FROM @ WeekDays**

| 数字 | 一天 | 名字 |
| --- | --- | --- |
| one | 孟人 | 星期一 |
| Two | 周二 | 星期二 |
| three | 结婚 | 星期三 |
| four | 星期四 | 星期四 |
| five | Fri | 星期五 |
| six | 坐 | 星期六 |
| seven | 太阳 | 星期日 |

**更新和删除 SQL Server 中表变量的语句用法**

这里我们将更新和删除表变量中的数据。

**示例-2 :**

```sql
DELETE @WeekDays WHERE Number=7;

UPDATE @WeekDays SET Name='Saturday is a holiday' WHERE Number=6 ;
SELECT * FROM @WeekDays;

```

| 数字 | 一天 | 名字 |
| --- | --- | --- |
| one | 孟人 | 星期一 |
| Two | 周二 | 星期二 |
| three | 结婚 | 星期三 |
| four | 星期四 | 星期四 |
| five | Fri | 星期五 |
| six | 坐 | 星期六是假日 |