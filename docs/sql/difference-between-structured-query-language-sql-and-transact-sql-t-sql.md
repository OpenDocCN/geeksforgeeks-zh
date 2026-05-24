# 结构化查询语言(SQL)与 Transact-SQL (T-SQL)的区别

> 原文:[https://www . geesforgeks . org/结构化查询语言差异-SQL-and-transact-SQL-t-SQL/](https://www.geeksforgeeks.org/difference-between-structured-query-language-sql-and-transact-sql-t-sql/)

**结构化查询语言(SQL):**
[结构化查询语言(SQL)](https://www.geeksforgeeks.org/structured-query-language/) 对数据的定义、访问和更改有特定的设计动机。它被认为是非程序性的，在这种情况下，重要元素及其结果首先被指定，而不考虑它们是如何计算的。它通过数据库引擎驱动的数据库来实现。数据库引擎的主要工作是解释 SQL 查询，并找到获取数据库中不同数据结构的访问技术。这也是用于评估结果准确性和效率的数据引擎的一个重要特征。

以下是 SQL–[DDL(数据定义语言)](https://www.geeksforgeeks.org/sql-ddl-dml-dcl-tcl-commands/)和 DML(数据操作语言)中包含的几组命令。DDL 用于描述和修改几种数据结构。而 DML 旨在访问和更改保存在 DDL 定义的数据结构中的数据。

**Transact-SQL(T-SQL):**
Transact-SQL(T-SQL)是 SQL 的扩展。它被认为是过程语言，不像 SQL 服务器使用的 SQL。它有助于执行从单行获取数据、添加新行、获取多行等操作。语法不同于其他类似 [PL-SQL](https://www.geeksforgeeks.org/plsql-introduction/) 的语法。但是，它具有与其他语言相同的功能并生成类似的结果。这是 SQL server 结构化查询语言的微软实现。

**结构化查询语言(SQL)和 Transact-SQL (T-SQL)的区别:**

<center>

| 没有。 | 比较 | 结构化查询语言 | T-SQL |
| 1. | 基础 | 这是非程序性的。 | 这是一个程序。 |
| 2. | 提供的功能 | 提供数据操作和控制功能 | 提供了过程编程函数和局部变量 |
| 3. | 特征 | 这是一种开放的语言 | 这是一个专有的 |
| 4. | 提交查询 | 一个接一个地 | 批量提交。 |
| 5. | 特殊特点 | 提供了几种 DDL、DML 和其他操作 | SQL 的所有特性以及事务控制、错误和异常处理。 |
| 6. | 得到 | 它是一种基础编程语言。 | 它源于 SQL，是 SQL 的增强形式。 |

</center>