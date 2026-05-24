# MS SQL Server 中的订单人

> 原文:[https://www.geeksforgeeks.org/order-by-in-ms-sql-server/](https://www.geeksforgeeks.org/order-by-in-ms-sql-server/)

在本文中，将讨论订购方以及与订购方相关的术语。

**简介–**

1.  In some cases, tables are arranged in chronological order.
2.  When users use the select statement to retrieve rows, there is no guarantee that the rows are in order.
3.  To solve this problem, the order by clause is being used.

**基本语法:**

```sql
select 
select_list
from
table_name
order by 
```

**示例:**样本表-学生

| 【卷号】 | 【 name 】 | [itinerary] |  |  |  | 【丽雅】 |
| --- | --- | --- | --- | --- | --- | --- |

如果用户想要按顺序排列姓名，那么查询必须写如下:

```sql
select
roll number 
name 
course
from
student
order by name 
```

输出结果是:

| Rolling number | name | schedule |
| --- | --- | --- |
|  |  | oil; fuel charging; make a greater effort |  |

请注意，默认情况下，使用 order by 子句按升序排列表格。

**ASC | DESC :**

1.  Users can use ASC or DESC to sort columns in ascending or descending order respectively.
2.  ASC arranges the columns from lowest to highest
3.  DESC arranges the columns from highest to lowest.
4.  If there is an empty column in the table, it will be regarded as the lowest value.