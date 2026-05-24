# SQL 中 JOIN、IN 和 EXISTS 子句的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-join-in-and-exists-clause-in-sql/](https://www.geeksforgeeks.org/difference-between-join-in-and-exists-clause-in-sql/)

SEQUEL 广为人知的 SQL，**结构化查询语言**是最流行的数据库标准语言。我们可以使用 SQL 执行大量操作，包括创建数据库、以表格形式存储数据、修改、提取等等。有不同版本的 SQL，如 `MYSQL`、`PostgreSQL`、`Oracle`、`SQL lite` 等。SQL 中有一些重要的命令，大致可以分为 `DDL`、`DML`、`DCL`、`TCL`、`DQL`。

在本文中，我们将区分 SQL 中三种不同的常用命令：

*   `IN`
*   `EXISTS`
*   `JOIN`

## IN 操作符

`IN` 操作符通常与 `WHERE` 子句一起使用，以测试给定的表达式或记录是否与一组值中的特定值相匹配。它的工作原理类似于多重 `OR` 运算符。`IN` 运算符的否定是 `NOT IN`，这有助于执行与值集不匹配的行。

**语法：**

```sql
SELECT column_name(s)
FROM table_name
WHERE col_name IN (val1, val2, val3, …..);
```

其中 `col_name` 是列的名称，`val` 是一组值。

**例：**

| Stud_id |
| :--- |
| 1 |
| 2 |
| 3 |

要获取来自古瓦哈蒂和帕特纳的学生的详细信息：

```sql
SELECT *
FROM Students
WHERE Stud_id IN (1, 3);
```

## EXISTS 操作符

`EXISTS` 操作符主要用于嵌套查询（一个查询里面的查询）。它用于检查子查询中提供的记录是否存在。如果一个或多个记录匹配，则返回布尔值 `TRUE`，否则返回 `FALSE`，如果没有行匹配，则返回 `FALSE`。类似地，像 `IN` 运算符一样，这里我们也可以使用 `EXISTS` 的否定，称为 `NOT EXISTS` 运算符。

**语法：**

```sql
SELECT column_name(s)
FROM table_name
WHERE EXISTS
(SELECT column_name(s)
FROM table_name
WHERE condition);
```

*其中条件：* 如果使用两个或两个以上的表，条件还应包含具有公共属性的 `column_matching` 信息。

**示例：**

采购表（`Purchases`）：

| Cust_id | Item |
| :--- | :--- |
| 1 | Mobile |
| 2 | TV |
| 1 | Laptop |

客户表（`Customers`）：

| Cust_id | Name | Email |
| :--- | :--- | :--- |
| 1 | Ramesh | ramesh@gmail.com |
| 2 | Khilan | khilan@gmail.com |

获取从电子商务网站购买手机的客户的姓名和电子邮件地址的详细信息。

```sql
SELECT Name, Email
FROM Customers
WHERE EXISTS (SELECT * FROM Purchases WHERE Cust_id = Customers.Cust_id AND Item = 'Mobile');
```

## JOIN 操作符

`JOIN` 用于在一些匹配列的基础上串联两个或多个表的元组或行。如果两个表中有任何条目不匹配，它将返回空值。SQL 中基本上有四种类型的联接：

1.  **内部连接**：返回两个表中匹配的值。
2.  **左连接**：左表中的所有记录（表 1）和右表中匹配的行（表 2）。
3.  **右连接**：右表中的所有记录（表 2）和左表中匹配的行（表 1）。
4.  **完全外部连接**：表 1 或表 2 中匹配的所有记录。

**语法：**

```sql
SELECT *
FROM table1
(JOIN TYPE) table2
ON table1.column_match = table2.column_match;
```

其中，`JOIN_TYPE` 是要执行的连接类型，无论是 `INNER JOIN`、`LEFT JOIN`、`RIGHT JOIN` 还是 `FULL JOIN`。`column_match` 是两个表中匹配的列。

对于以上相同的表格 `Purchases` 和 `Customers`，让我们看看不同的 `JOIN` 运算符执行什么操作：

*   **使用 `INNER JOIN`：**

```sql
SELECT Customers.Name, Purchases.Item
FROM Customers
INNER JOIN Purchases ON Customers.Cust_id = Purchases.Cust_id;
```

*   **使用 `LEFT JOIN`：**

```sql
SELECT Customers.Name, Purchases.Item
FROM Customers
LEFT JOIN Purchases ON Customers.Cust_id = Purchases.Cust_id;
```

*   **使用 `RIGHT JOIN`：**

```sql
SELECT Customers.Name, Purchases.Item
FROM Customers
RIGHT JOIN Purchases ON Customers.Cust_id = Purchases.Cust_id;
```

*   **使用 `FULL JOIN`：**

```sql
SELECT Customers.Name, Purchases.Item
FROM Customers
FULL JOIN Purchases ON Customers.Cust_id = Purchases.Cust_id;
```

## SQL 中 JOIN、IN 和 EXISTS 子句的区别

| 特性 | IN | EXISTS | JOIN |
| :--- | :--- | :--- | :--- |
| 工作原理 | 类似于多个 `OR` 运算符。因此，它避免了在查询中多次编写 `OR`。 | 如果找到匹配项，则返回 `TRUE` 值。 | 用于将两个或多个表连接成一个表。 |
| 执行方式 | 将扫描 `IN` 操作符内的所有值，然后做出决策。 | 如果获得单个条件的 `TRUE` 值，它将停止执行。 | 首先检查是否存在匹配，然后基于两个表的匹配列连接两个表。 |
| 返回值 | 返回 `TRUE`、`FALSE` 和 `NULL` 值。 | 返回 `TRUE` 或 `FALSE`。 | 如果没有匹配，则在连接表中返回空条目。 |
| 用途 | 可用于嵌套查询和上述示例中的值。 | 仅用于嵌套查询。 | `JOIN` 也可与嵌套查询一起使用。 |
| 效率 | 当 `IN` 与子查询一起使用时，效率较低，因为关系数据库将首先执行整个子查询，然后最终根据指定条件执行。然而，对于较大的关系表，`IN` 在子查询中可能比 `EXISTS` 和 `JOIN` 工作得更快。 | 在 `EXISTS` 的情况下，我们知道它将根据用户指定的条件返回 `TRUE` 或 `FALSE`。因此，对于子查询中的小表条目，`EXISTS` 比 `IN` 更有效。 | 类似于 `EXISTS` 操作符。如果子查询表的数据相对较小，执行效率将高于 `IN`。 |