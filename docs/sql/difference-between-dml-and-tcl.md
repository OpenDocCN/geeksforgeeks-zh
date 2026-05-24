# DML 和 TCL 的区别

> 原文:[https://www . geesforgeks . org/difference-DML-and-TCL/](https://www.geeksforgeeks.org/difference-between-dml-and-tcl/)

先决条件–[DDL、DML、TCL 和 DCL](https://www.geeksforgeeks.org/sql-ddl-dml-tcl-dcl/)
**1。数据操作语言(DML) :**
DML 用于操作数据库中的数据。例如 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 中的插入、更新、删除指令。

**2。事务控制语言(TCL) :**
TCL 处理数据库中的事务。

**DML 与 TCL 的区别:**

<figure class="table">

| s No. | category | DoctorofModernLanguages 现代语言博士 | TCL 集团股份有限公司（TCL Corporation 的缩写） |
| --- | --- | --- | --- |
| 1。 | Complete form | DML stands for data operation language. | TCL stands for transaction control language. |
| 2。 | definition | DML stands for data manipulation language, which is used to manipulate data in the database by performing insert, update and delete operations. | Transaction control language (TCL) is composed of commands for processing transactions in the database.
 |
| 3。 | classify | Data modification languages are further divided into procedural and non-procedural DML. | Transaction control languages are not further classified. |
| 4。 | Characteristic display of database management system | It shows the easy-to-maintain features of (files). | Show the characteristics of atomicity. |
| 5。 | Use in transactions | DML cannot be used for database transactions. | TCL is used to handle database transactions. |
| 6。 | sequence | DML statements are usually written before TCL statements in queries. | TCL statements are usually written after DML statements in queries. |
| 7。 | Use log files | It does not use log files. | It uses log files to keep records of all transactions. |
| 8。 | order | Commands commonly used in DML include: update, insert, merge, select, delete, call, explain plan and lock table. | Commonly used commands in TCL include: submit, rollback, savepoint and set transaction. |
| 9。 | by | Handling DML is handled by the query compiler and query optimizer of DBMS architecture. | TCL is handled by transaction manager and recovery manager. |
| 10。 | locking | It uses locks for concurrency control. | Do not use locks. |
| Eleven. | WHERE clause | Most DML statements have WHERE clauses to filter them. | TCL does not need a WHERE clause. |
| Twelve. | Data access path | DML can be used to explain the access path of data. | TCL cannot explain the data access path. |
| Thirteen. | call subroutine | Used to call PL/SQL or Java subprograms. | Not used to call subroutines. |
| 14。 | Merge operation | We can use DML to merge. | TCL cannot perform the merge operation. |
| Fifteen. | trigger | Trigger fires after DML statement. | TCL is not used for triggers. |
| 16。 | example | Example of SQL query to find the names of all lecturers in the history department:
Select the names
From lecturers [T2】 WHERE dept _ name =' History '；;
 | 我们将使用 commit 命令永久保存表记录。如果我们想将乔利的名字更新为夏洛克并永久保存，我们可以使用以下内容，
更新学生
设置名称= '夏洛克'
其中名称= '乔利'；COMMIT；
回滚； |

</figure>