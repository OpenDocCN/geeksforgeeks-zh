# SQL Server 中的 RANK()函数

> 原文:[https://www.geeksforgeeks.org/rank-function-in-sql-server/](https://www.geeksforgeeks.org/rank-function-in-sql-server/)

**RANK()函数**是一个[窗口函数](https://www.geeksforgeeks.org/window-functions-in-sql/)，可以在 [SQL Server](https://www.geeksforgeeks.org/sql-tutorial/) 中使用，为结果集的一个分区内的每一行计算一个等级。

相同的等级被分配给分区中具有相同值的行。第一行的排名是 1。在 **RANK()函数**中，等级可能不是连续的，因为它将重复的行数添加到重复的等级中，以计算下一行的等级。

**语法:**

```sql
RANK() OVER (
   [PARTITION BY expression, ]
   ORDER BY expression (ASC | DESC) );

```

**示例–**
让我们创建一个只有列名的表 geek_demo:

```sql
CREATE TABLE geek_demo (Name VARCHAR(10) );

```

现在，在 sales.rank_demo 表中插入一些行:
插入 geek_demo(名称)

```sql
VALUES('A'), ('B'), ('B'), ('C'), ('C'), ('D'), ('E');

```

从 geek_demo 表中选择数据:

```sql
SELECT * 
FROM sales.geek_demo; 

```

| 名字 |
| --- |
| A |
| B |
| B |
| C |
| C |
| D |
| E |

让我们使用 RANK()为 geek_demo 表的结果集中的行分配等级:

```sql
SELECT Name, 
RANK () OVER (
ORDER BY Name
) AS Rank_no 
FROM geek_demo;

```

**输出–**

| 名字 | ranknow |
| --- | --- |
| A | one |
| B | Two |
| B | Two |
| C | four |
| C | four |
| D | six |
| E | seven |