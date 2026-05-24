# SQL 中的 ORDER BY 子句和 GROUP BY 子句之间的差异

> 原文: [https://www.geeksforgeeks.org/difference-between-order-by-and-group-by-clause-in-sql/](https://www.geeksforgeeks.org/difference-between-order-by-and-group-by-clause-in-sql/)

## 1. ORDER BY

`ORDER BY` 关键字以升序或降序对结果集进行排序。默认情况下，此子句按升序对结果集进行排序。为了按降序对结果集进行排序，使用了 `DESC` 关键字。

**语法：**

```sql
SELECT column_1, column_2, column_3...........
FROM Table_Name
ORDER BY column_1, column_2, column_3....... ASC|DESC;

Table_Name: Name of the table.
ASC: keyword for ascending order
DESC: keyword for descending order 
```

## 2. GROUP BY

`GROUP BY` 语句用于对具有相同值的行进行分组。它经常与聚合函数一起使用，例如：`AVG()`、`MAX()`、`COUNT()`、`MIN()` 等。关于 `GROUP BY` 子句需要记住的一点是，元组是根据元组属性值之间的相似性进行分组的。

**语法：**

```sql
SELECT function_Name(column_1), column_2
FROM Table_Name
WHERE condition
GROUP BY column_1, column_2
ORDER BY column_1, column_2; 
```

函数名：聚合函数的名称，例如：

```sql
SUM(), AVG(), COUNT() etc.

Table_Name: Name of the table. 
```

让我们看看 `GROUP BY` 子句和 `ORDER BY` 子句的区别：

| S.NO | GROUP BY | ORDER BY |
| --- | --- | --- |
| 1. | `GROUP BY` 语句用于对具有相同值的行进行分组。 | 而 `ORDER BY` 语句以升序或降序对结果集进行排序。 |
| 2. | 它可能在 `CREATE VIEW` 语句中被允许。 | 而它在 `CREATE VIEW` 语句中不使用。 |
| 3. | 在 `SELECT` 语句中，它总是用在 `ORDER BY` 关键字之前。 | 而在 `SELECT` 语句中，它总是用在 `GROUP BY` 关键字之后。 |
| 4. | 属性不能在聚合函数下的 `GROUP BY` 语句中。 | 而 `ORDER BY` 语句，属性可以在聚合函数下。 |
| 5. | 在 `GROUP BY` 子句中，元组根据元组属性值之间的相似性进行分组。 | 而在 `ORDER BY` 子句中，结果集是根据升序或降序排序的。 |
| 6. | `GROUP BY` 控制元组（行）的表示。 | 而 `ORDER BY` 子句控制列的显示。 |