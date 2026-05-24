# 微软服务器中的 Where 子句

> 原文:[https://www . geesforgeks . org/where-子句-in-ms-sql-server/](https://www.geeksforgeeks.org/where-clause-in-ms-sql-server/)

在本文中，where 子句将与示例一起讨论。

**简介:**

1.  To extract time data, we need a specific condition to meet.
2.  "where" is a clause used to write conditions in a query.

**语法:**

```sql
select select_list
from table_name
where condition
```

下面给出了一个例子，以便更好地说明–

**示例:**

**样表:学生**

| 【卷号】 | 【 name 】 | [itinerary] |  |  |  | 【丽雅】 |
| --- | --- | --- | --- | --- | --- | --- |

如果用户想提取正在攻读机械的学生姓名，查询如下:

```sql
select name
from student
where course='Mechanical' 
```

输出是–

| 【 name 】 | [itinerary] |
| --- | --- |
| [mine] | 【机械】 |

“where”条件仅筛选评估为 true 的行。如果条件评估为 false 或未知，则不会筛选行，从而导致错误。