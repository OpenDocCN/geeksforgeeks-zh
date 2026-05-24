# MS SQL Server 中的 ORDER BY

> 原文：[https://www.geeksforgeeks.org/order-by-in-ms-sql-server/](https://www.geeksforgeeks.org/order-by-in-ms-sql-server/)

在本文中，将讨论 `ORDER BY` 以及与之相关的术语。

## 简介

1.  在某些情况下，表是按时间顺序排列的。
2.  当用户使用 `SELECT` 语句检索行时，无法保证返回的行是有序的。
3.  为了解决这个问题，就需要使用 `ORDER BY` 子句。

## 基本语法

```sql
SELECT 
    select_list
FROM
    table_name
ORDER BY 
```

## 示例

样本表 - 学生

| 【卷号】 | 【 name 】 | [itinerary] |  |  |  | 【丽雅】 |
| --- | --- | --- | --- | --- | --- | --- |

如果用户想要按顺序排列姓名，那么查询必须写如下：

```sql
SELECT
    roll_number,
    name,
    course
FROM
    student
ORDER BY name;
```

输出结果是：

| Rolling number | name | schedule |
| --- | --- | --- |
|  |  | oil; fuel charging; make a greater effort |

请注意，默认情况下，使用 `ORDER BY` 子句按升序排列表格。

## ASC | DESC

1.  用户可以使用 `ASC` 或 `DESC` 分别按升序或降序对列进行排序。
2.  `ASC` 将列从最低值排列到最高值。
3.  `DESC` 将列从最高值排列到最低值。
4.  如果表中存在空列，它将被视为最低值。