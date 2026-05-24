# DML 和 TCL 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-dml-and-tcl/](https://www.geeksforgeeks.org/difference-between-dml-and-tcl/)

先决条件：[DDL、DML、TCL 和 DCL](https://www.geeksforgeeks.org/sql-ddl-dml-tcl-dcl/)

**1. 数据操作语言 (DML)：**
DML 用于操作数据库中的数据。例如 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 中的 `INSERT`、`UPDATE`、`DELETE` 指令。

**2. 事务控制语言 (TCL)：**
TCL 处理数据库中的事务。

**DML 与 TCL 的区别：**

| 序号 | 类别 | DML (数据操作语言) | TCL (事务控制语言) |
| :--- | :--- | :--- | :--- |
| 1 | 完整形式 | DML 代表数据操作语言。 | TCL 代表事务控制语言。 |
| 2 | 定义 | DML 代表数据操作语言，用于通过执行 `INSERT`、`UPDATE` 和 `DELETE` 操作来操作数据库中的数据。 | 事务控制语言 (TCL) 由用于处理数据库中事务的命令组成。 |
| 3 | 分类 | 数据操作语言进一步分为过程式和非过程式 DML。 | 事务控制语言不再进一步分类。 |
| 4 | 数据库管理系统特性展示 | 它展示了（文件）易于维护的特性。 | 展示了原子性特性。 |
| 5 | 在事务中的使用 | DML 不能用于数据库事务。 | TCL 用于处理数据库事务。 |
| 6 | 顺序 | 在查询中，DML 语句通常写在 TCL 语句之前。 | 在查询中，TCL 语句通常写在 DML 语句之后。 |
| 7 | 使用日志文件 | 它不使用日志文件。 | 它使用日志文件来记录所有事务。 |
| 8 | 常用命令 | DML 中常用的命令包括：`UPDATE`、`INSERT`、`MERGE`、`SELECT`、`DELETE`、`CALL`、`EXPLAIN PLAN` 和 `LOCK TABLE`。 | TCL 中常用的命令包括：`COMMIT`、`ROLLBACK`、`SAVEPOINT` 和 `SET TRANSACTION`。 |
| 9 | 处理者 | DML 由 DBMS 架构中的查询编译器和查询优化器处理。 | TCL 由事务管理器和恢复管理器处理。 |
| 10 | 锁定 | 它使用锁进行并发控制。 | 不使用锁。 |
| 11 | WHERE 子句 | 大多数 DML 语句都有 `WHERE` 子句进行过滤。 | TCL 不需要 `WHERE` 子句。 |
| 12 | 数据访问路径 | DML 可用于解释数据的访问路径。 | TCL 不能解释数据访问路径。 |
| 13 | 调用子程序 | 用于调用 PL/SQL 或 Java 子程序。 | 不用于调用子程序。 |
| 14 | 合并操作 | 我们可以使用 DML 进行合并。 | TCL 不能执行合并操作。 |
| 15 | 触发器 | 触发器在 DML 语句之后触发。 | TCL 不用于触发器。 |
| 16 | 示例 | 查找历史系所有讲师姓名的 SQL 查询示例：
```sql
SELECT name
FROM lecturers
WHERE dept_name = 'History';
```
| 我们将使用 `COMMIT` 命令永久保存表记录。如果我们想将 `Chloe` 的名字更新为 `Sherlock` 并永久保存，我们可以使用以下内容：
```sql
UPDATE students
SET name = 'Sherlock'
WHERE name = 'Chloe';
COMMIT;
ROLLBACK;
``` |