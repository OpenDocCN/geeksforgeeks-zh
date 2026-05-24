# 微软 SQL Server 中的 HAVING 子句

> 原文: [https://www.geeksforgeeks.org/having-clause-in-ms-sql-server/](https://www.geeksforgeeks.org/having-clause-in-ms-sql-server/)

在本文中，我们将讨论微软的 SQL Server 中的 `HAVING` 子句。

在某些情况下，要从查询中提取的数据是使用特定条件完成的。为此，使用了 `HAVING` 子句。`HAVING` 子句根据用户在查询中给出的条件提取行。`HAVING` 子句必须与 `GROUP BY` 子句配对才能提取数据。否则，会产生错误。

## 语法

```
SELECT 
    select_list
FROM
    table_name
GROUP BY
    group_list
HAVING 
    conditions
```

## 示例

| Roll Number | Name | Course |
| --- | --- | --- |
| 111 | Riya | SSE |
| 112 | Taniya | ECE |
| 113 | Minakshi | IT |
| 114 | Rita | Biotechnology |
| 115 | Sangeeta | Chemistry |
| 116 | Deepa | EEE |

假设用户想要从 `student` 表中提取姓名以 `R` 开头的学生的学号，查询如下：

```
SELECT roll_number
FROM student 
HAVING name LIKE 'R%'
```

输出将显示一个错误。这是因为查询中没有包含 `GROUP BY` 子句。
为获得所需结果而修改的查询如下：

```
SELECT roll_number 
FROM student 
GROUP BY name
HAVING name LIKE 'R%'
```

输出如下：

| Roll Number | Name |
| --- | --- |
| 114 | Rita |
| 111 | Riya |

`WHERE` 子句通常用于通过包含条件来提取查询。`WHERE` 和 `HAVING` 子句，两者都用于使用特定条件提取数据。然而，`HAVING` 子句通过基于组列表进行分组来提取数据，`WHERE` 子句通过插入条件来直接提取数据。