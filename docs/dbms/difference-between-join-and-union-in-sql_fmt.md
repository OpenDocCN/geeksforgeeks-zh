# SQL 中 JOIN 和 UNION 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-join-and-union-in-sql/](https://www.geeksforgeeks.org/difference-between-join-and-union-in-sql/)

## JOIN
SQL 中的 `JOIN` 用于根据多个表之间的匹配条件组合来自这些表的数据。使用 `JOIN` 语句组合的数据会生成新的列。

考虑两个表：

**男生**
![](img/c49574fecc9a42ac02bc6eda2a1d4da8.png)

**女生**
![](img/3cc5e67fda117bba02f3e59447104155.png)

### 示例
```sql
SELECT Boys.Name, Boys.Age, Girls.Address,
FROM Boys 
INNER JOIN Girls 
ON Boys.Rollno = Girls.Rollno; 
```

结果表格为：
![](img/29c717f56f1c5b1cb429bddc677803c4.png)

## UNION
`UNION` 在 SQL 中用于组合两个或多个 `SELECT` 语句的结果集。使用 `UNION` 语句组合的数据被转换成新的不同行的结果。

### 示例
```sql
SELECT Name 
FROM Boys 
WHERE Rollno < 16

UNION

SELECT Name 
FROM Girls 
WHERE Rollno > 9 
```

结果表格为：
![](img/787d9b3d4663d99d822f8c6d8ae3b258.png)

## SQL 中 JOIN 和 UNION 的区别

| JOIN | UNION |
| --- | --- |
| `JOIN` 根据许多表之间的匹配条件组合这些表中的数据。 | `UNION` 组合了两个或多个 `SELECT` 语句的结果集。 |
| 它将数据组合成新的列。 | 它将数据组合成新的行。 |
| 从每个表中选择的列数可能不相同。 | 从每个表中选择的列数应该相同。 |
| 从每个表中选择的相应列的数据类型可以不同。 | 从每个表中选择的相应列的数据类型应该相同。 |
| 它可能不会返回不同的行。 | 它返回不同的行。 |