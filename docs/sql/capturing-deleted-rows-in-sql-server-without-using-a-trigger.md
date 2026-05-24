# 在不使用触发器的情况下捕获 SQL Server 中已删除的行

> 原文:[https://www . geesforgeks . org/capture-deleted-row-in-SQL-server-不使用触发器/](https://www.geeksforgeeks.org/capturing-deleted-rows-in-sql-server-without-using-a-trigger/)

**简介:**

使用[触发器](https://www.geeksforgeeks.org/sql-triggers/)有时会很困难且耗时。触发器会降低服务器的输出速度，并给系统资源带来额外的压力。许多人使用触发器来跟踪从表中删除的所有数据。我们可以使用另一个过程，而不是使用触发器，如下例所示。请注意，以下安排不能替代删除触发器。另一方面，如果我们只想记录删除的行，我们可以用它来代替触发器。

**示例:**
让我们创建两个表–

```sql
CREATE TABLE GeekTab1 (Id1 INT, Name1 VARCHAR(100))
GO
CREATE TABLE GeekTab2 (Id2 INT, Name2 VARCHAR(100))
GO
```

将样本数据插入表格–

```sql
INSERT INTO GeekTab1 (Id1, Name1)
VALUES(1,'Khushi'), (2, 'Komal')
GO
```

从表中选择数据–

```sql
Select * from GeekTab1
GO
```

**输出–**

<figure class="table">

| Id1 | 名称 1 |
| --- | --- |
| one | 库希 |
| Two | 科马尔 |

T27】</figure>

从极客标签 1 中删除并插入极客标签 2–

```sql
DELETE FROM GeekTab1
OUTPUT deleted.Id1, deleted.Name1
INTO GeekTab2
WHERE Id1 = 1
GO
```

从两个表中选择数据–

```sql
SELECT * FROM GeekTab1;
GO
SELECT * FROM GeekTab2;
GO
```

**输出–**

**geek tab 1**

<figure class="table">

| Id1 | 名称 1 |
| --- | --- |
| Two | 科马尔 |

T21】</figure>

**geek tab 2**

<figure class="table">

| Id2 | 名称 2 |
| --- | --- |
| one | 库希 |

T21】</figure>

**结论:**
OUTPUT 子句用于上述情况下的 DELETE 语句中，它记录了从 GeekTab1 中删除的语句。