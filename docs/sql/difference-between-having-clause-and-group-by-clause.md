# Having 子句和 Group by 子句的区别

> 原文:[https://www . geesforgeks . org/having-子句和 group-by-子句的区别/](https://www.geeksforgeeks.org/difference-between-having-clause-and-group-by-clause/)

**1。Having 子句:**
Having 子句基本上类似于 GROUP BY 子句的聚合函数。HAVING 子句用于聚合函数，而不是 WHERE。而**分组依据**子句将具有相同值的行分组到汇总行中。having 子句与 where 子句一起使用，以便查找具有特定条件的行。having 子句总是用在 group By 子句之后。

```sql
SELECT COUNT (SALARIES) AS COUNT_SALARIES, EMPLOYEES
FROM EMPLOYEES
GROUP BY SALARIES
HAVING COUNT(SALARIES) > 1; 
```

**2。**[**【Group By 子句】**](https://www.geeksforgeeks.org/sql-group-by/)**:**
Group By 子句通常与聚合函数(MAX、SUM、AVG)一起使用，将结果按一列或多列分组，或者简单地说，我们可以说 Group By 子句与 SELECT 语句一起使用，将所需数据排列成组。
GROUP BY 语句对具有相同值的行进行分组。此语句用在 where 子句之后。这个语句经常和一些聚合函数一起使用，比如 SUM，AVG，COUNT atc。按一列或多列对结果进行分组。

```sql
SELECT COUNT (SALARIES) AS COUNT_SALARIES, EMPLOYEES
FROM EMPLOYEES
GROUP BY SALARIES; 
```

**Having 子句与 Group by 子句的区别:**

<figure class="table">

| s。没有。 | 拥有子句 | (西班牙语) |
| --- | --- | --- |
| 1。 | Used to apply some additional conditions to the query. | Group clause is used to group data according to specific columns or rows. |
| 2。 | Having can be used without the groupby clause. In aggregate functions, in this case, its behavior is similar to the where clause. | Groupby can use the select statement without clause. |
| 3。 | The having clause can contain aggregate functions. | Cannot contain aggregate functions. |
| 4。 | Use some conditions to limit query output. | Group outputs according to some rows or columns. |

</figure>