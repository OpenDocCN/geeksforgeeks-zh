# TCL 完整形式

> 原文: [https://www.geeksforgeeks.org/tcl-full-form/](https://www.geeksforgeeks.org/tcl-full-form/)

**TCL** 代表**交易控制语言**。这些命令用于维护数据库的一致性和管理由 DML 命令进行的事务。

一个**事务**是一组 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 语句，对存储在数据库管理系统中的数据执行。无论何时进行任何事务，这些事务都暂时发生在数据库中。因此，为了使更改永久化，我们使用 **TCL** 命令。

TCL 命令包括:

1.  COMMIT
2.  ROLLBACK
3.  SAVEPOINT

## COMMIT

此命令用于永久保存数据。
每当我们执行任何 DML 命令，如 `INSERT`、`DELETE` 或 `UPDATE`，如果数据没有永久存储，这些操作都可以回滚。所以为了安全起见，使用了 `COMMIT` 命令。

**语法:**

```sql
commit;
```

## ROLLBACK

此命令用于获取数据或将数据恢复到最后一个保存点或最后一次提交的状态。如果由于某些原因，`INSERT`、`DELETE` 或 `UPDATE` 的数据不正确，您可以将数据回滚到特定的保存点，或者如果保存点没有完成，则回滚到上次提交的状态。

**语法:**

```sql
rollback;
```

## SAVEPOINT

该命令用于临时保存特定点的数据，以便在需要时可以回滚到该特定点。

**语法:**

```sql
Savepoint A;
```

考虑以下表格 `STUDENT`:

| name | mark |
| --- | --- |
| John | 79 |
| Jolly | 65 |
| Shuzan | 70 |

```sql
UPDATE STUDENT 
SET NAME = ‘Sherlock’ 
WHERE NAME = ‘Jolly’;

COMMIT;
ROLLBACK;
```

使用此命令，您可以使用 `COMMIT` 命令更新记录并永久保存。

现在在 `COMMIT` 之后:

| name | mark |
| --- | --- |
| John | 79 |
| Sherlock | 65 |
| Shuzan | 70 |

如果未执行 `COMMIT`，则 `UPDATE` 命令所做的更改可以回滚。

现在如果没有执行 `COMMIT`。

```sql
UPDATE STUDENT 
SET NAME = ‘Sherlock’ 
WHERE STUDENT_NAME = ‘Jolly’;
```

`UPDATE` 命令后该表将为:

| name | mark |
| --- | --- |
| John | 79 |
| Shylock | 65 |
| Shuzan | 70 |

现在如果在上表中执行 `ROLLBACK`:

```sql
rollback;
```

回滚后:

| name | mark |
| --- | --- |
| John | 79 |
| Jolly | 65 |
| Shuzan | 70 |

如果在上表中执行了保存点:

```sql
INSERT into STUDENT 
VALUES ('Jack', 95);

Commit;

UPDATE STUDENT 
SET NAME= ‘Rossie’ 
WHERE marks= 70;

SAVEPOINT A;

INSERT INTO STUDENT 
VALUES (‘Zack’, 76);

Savepoint B;

INSERT INTO STUDENT 
VALUES (‘Bruno’, 85);

Savepoint C;

SELECT * 
FROM STUDENT;
```

| name | mark |
| --- | --- |
| John | 79 |
| Shylock | 65 |
| Rossie | 70 |
| Jack | 95 |
| Zack | 76 |
| Bruno | 85 |

现在，如果我们回滚到保存点 B:

```sql
Rollback to B;
```

由此产生的表格将是:

| name | mark |
| --- | --- |
| John | 79 |
| Shylock | 65 |
| Rossie | 70 |
| Jack | 95 |

现在，如果我们回滚到保存点 A:

```sql
Rollback to A;
```

由此产生的表格将是:

| name | mark |
| --- | --- |
| John | 79 |
| Shylock | 65 |
| Rossie | 70 |

所以这都是关于 SQL (事务控制语言) 中的 **TCL** 命令的例子。