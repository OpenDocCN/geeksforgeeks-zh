# SQL Server 中的平均值和模式

> 原文:[https://www.geeksforgeeks.org/find-mean-mode-sql-server/](https://www.geeksforgeeks.org/find-mean-mode-sql-server/)

**均值**是给定数据集的平均值，计算方法是将总和除以数据集中的数值数。

示例:

```sql
Input:  1, 2, 3, 4, 5 
Output: 3
Explanation: 
sum = 1 + 2 + 3 + 4 + 5 = 15
number of values = 5
mean = 15 / 5 = 3

```

**查询查找表中的平均值**

```sql
SELECT Avg(Column_Name) 
FROM  Table_Name

```

**示例:**

**创建表格:**
![](img/d3a791ed64febfa93f90d36abf725690.png)

**表格内容:**
![](img/082923e82d0dded7f09d90826f4eea46.png)

**查询找到均值:**
![](img/f436fb36934ec663ef9c889c47551b55.png)

**数据集的模式**是一系列数据中出现频率最高的值。

示例:

```sql
Input:  1, 2, 2, 3, 4, 4, 4, 5, 5, 6
Output: 4
Explanation:
2 occurs 2 times, 5 occurs 2 times
4 occurs 3 times and rest other 
occurs 1 time
So, 4 occurs most frequently and 
is thus the output.

```

**查询查找表中的模式**

```sql
SELECT TOP 1 Column_Name
FROM   Table_name
GROUP  BY [Column_Name]
ORDER  BY COUNT(*) DESC

```

**示例:**

**创建表格:**
![](img/49d2bf4dada5d6375db6c7e1b6c0dd49.png)

**表格内容:**
![](img/77e43f7503ffd1cf025ea39cecc18acf.png)

**查询查找方式:**
![](img/8590c3f393976226f23020bb1f220687.png)