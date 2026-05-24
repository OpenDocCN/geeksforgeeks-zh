# 在 SQL Server 中使用一条语句将多个值插入到多个表中

> 原文: [https://www.geeksforgeeks.org/insert-multiple-values-into-multiple-tables-using-a-single-statement-in-sql-server/](https://www.geeksforgeeks.org/insert-multiple-values-into-multiple-tables-using-a-single-statement-in-sql-server/)

2005 年引入的 T-SQL 函数 `OUTPUT` 可用于在一条语句中将多个值插入多个表中。作为 `INSERT`、`UPDATE` 或 `DELETE` 操作一部分的每一行的输出值都由 `OUTPUT` 子句返回。

## 语法

```sql
INSERT INTO Table1 (Col1, Col2)
OUTPUT inserted.Col1, inserted.Col2
INTO Table2
VALUES()
GO
```

## 示例

让我们使用以下查询创建两个示例表：

```sql
CREATE TABLE GeekTable1 (Id1 INT, Name1 VARCHAR(200), City1 VARCHAR(200))
GO
CREATE TABLE GeekTable2 (Id2 INT, Name2 VARCHAR(200), City2 VARCHAR(200))
GO
```

现在让我们一起将值插入两个表中：

```sql
INSERT INTO GeekTable1 (Id1, Name1, City1)
OUTPUT inserted.Id1, inserted.Name1, inserted.City1
INTO GeekTable2
VALUES(1,'Komal'), (2, 'Khushi')
GO
```

从两个表中选择数据：

```sql
SELECT * FROM GeekTable1 ;
GO
SELECT * FROM GeekTable2 ;
GO
```

## 输出

当我们运行上面的查询时，我们会看到表中各有两行。

**GeekTable1**

| Id1 | Name1 | City1 |
| --- | --- | --- |
| 1 | Komal | NULL |
| 2 | Khushi | NULL |

**GeekTable2**

| Id2 | Name2 | City2 |
| --- | --- | --- |
| 1 | Komal | NULL |
| 2 | Khushi | NULL |