# Having 子句和 Group by 子句的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-having-clause-and-group-by-clause/](https://www.geeksforgeeks.org/difference-between-having-clause-and-group-by-clause/)

## 1. Having 子句

`Having` 子句基本上类似于 `GROUP BY` 子句的聚合函数。`HAVING` 子句用于聚合函数，而不是 `WHERE`。而 `GROUP BY` 子句将具有相同值的行分组到汇总行中。`having` 子句与 `where` 子句一起使用，以便查找具有特定条件的行。`having` 子句总是用在 `group By` 子句之后。

```sql
SELECT COUNT (SALARIES) AS COUNT_SALARIES, EMPLOYEES
FROM EMPLOYEES
GROUP BY SALARIES
HAVING COUNT(SALARIES) > 1; 
```

## 2. Group By 子句

`Group By` 子句通常与聚合函数（`MAX`、`SUM`、`AVG`）一起使用，将结果按一列或多列分组，或者简单地说，我们可以说 `Group By` 子句与 `SELECT` 语句一起使用，将所需数据排列成组。
`GROUP BY` 语句对具有相同值的行进行分组。此语句用在 `where` 子句之后。这个语句经常和一些聚合函数一起使用，比如 `SUM`，`AVG`，`COUNT` 等。按一列或多列对结果进行分组。

```sql
SELECT COUNT (SALARIES) AS COUNT_SALARIES, EMPLOYEES
FROM EMPLOYEES
GROUP BY SALARIES; 
```

## Having 子句与 Group by 子句的区别

| 序号 | Having 子句 | Group By 子句 |
| :--- | :--- | :--- |
| 1. | 用于对查询应用一些额外条件。 | 用于根据特定的列或行对数据进行分组。 |
| 2. | 可以在没有 `groupby` 子句的情况下使用。在聚合函数中，这种情况下其行为类似于 `where` 子句。 | 可以在没有子句的情况下使用 `select` 语句。 |
| 3. | `having` 子句可以包含聚合函数。 | 不能包含聚合函数。 |
| 4. | 使用一些条件来限制查询输出。 | 根据某些行或列对输出进行分组。 |