# 删除和截断的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-delete-and-truncate/](https://www.geeksforgeeks.org/difference-between-delete-and-truncate/)

## 1. DELETE

`DELETE` 是一个 [`DML(数据操作语言)`](https://www.geeksforgeeks.org/difference-between-ddl-and-dml-in-dbms/) 命令，在我们指定要从表或关系中删除的行（元组）时使用。`DELETE` 命令可以包含一个 `WHERE` 子句。如果 `WHERE` 子句与 `DELETE` 命令一起使用，那么它只删除或删除那些满足条件的行（元组），否则默认情况下，它从表中删除所有元组（行）。

**DELETE 命令语法：**

```sql
DELETE FROM TableName 
WHERE condition; 
```

## 2. TRUNCATE

`TRUNCATE` 是一个 [`DDL(数据定义语言)`](https://www.geeksforgeeks.org/difference-between-ddl-and-dml-in-dbms/) 命令，用于删除表中的所有行或元组。与 `DELETE` 命令不同，`TRUNCATE` 命令不包含 `WHERE` 子句。在 `TRUNCATE` 命令中，会记录每个已删除数据页的事务日志。与 `DELETE` 命令不同，`TRUNCATE` 命令速度很快。在使用 `TRUNCATE` 命令后，我们无法回滚数据。

**TRUNCATE 命令的语法：**

```sql
TRUNCATE TABLE TableName; 
```

## 3. DELETE 和 TRUNCATE 的区别

让我们看看 `DELETE` 和 `TRUNCATE` 命令之间的区别：

| S.NO | `DELETE` | `TRUNCATE` |
| :--- | :--- | :--- |
| 1. | `DELETE` 命令用于删除指定的行（一行或多行）。 | 此命令用于删除表中的所有行。 |
| 2. | 是一个 `DML`（数据操作语言）命令。 | 是一个 `DDL`（数据定义语言）命令。 |
| 3. | 为了过滤记录，`DELETE` 命令中可能包含 `WHERE` 子句。 | `TRUNCATE` 命令中可能没有 `WHERE` 子句。 |
| 4. | 在 `DELETE` 命令中，元组在被删除前会被锁定。 | 在此命令中，表数据在被删除前，其数据页会被锁定。 |
| 5. | `DELETE` 语句一次删除一行，并为每个删除的行在事务日志中记录一条条目。 | `TRUNCATE TABLE` 通过释放用于存储表数据的数据页来移除数据，并且只有页释放操作会被记录在事务日志中。 |
| 6. | `DELETE` 命令比 `TRUNCATE` 命令慢。 | `TRUNCATE` 命令比 `DELETE` 命令快。 |
| 7. | 要使用 `DELETE`，你需要对表拥有 `DELETE` 权限。 | 要在表上使用 `TRUNCATE`，我们至少需要对表拥有 `ALTER` 权限。 |
| 8. | 在表中使用 `DELETE` 语句后，标识列的标识值会保留。 | 如果表包含标识列，该列的标识值将被重置为其种子值。 |
| 9. | `DELETE` 可用于索引视图。 | `TRUNCATE` 不能用于索引视图。 |