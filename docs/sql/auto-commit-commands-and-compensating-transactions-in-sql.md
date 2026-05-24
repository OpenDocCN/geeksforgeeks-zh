# SQL 中的自动提交命令和补偿事务

> 原文:[https://www . geesforgeks . org/auto-commit-command-compensive-transactions-in-SQL/](https://www.geeksforgeeks.org/auto-commit-commands-and-compensating-transactions-in-sql/)

顾名思义，**自动提交语句**用于避免在每个 SQL 语句后明确提到提交命令。提交语句本身在每个 SQL 语句之后由服务器执行。每个 SQL 语句都被视为不同的事务。在自动提交模式下执行的 SQL 语句无法回滚。

**自动提交命令:**

SQL 中有四个自动提交命令，它们是:

1.  **将自动提交设置为开启–**
    通过执行该特定命令，自动提交状态变为开启(如果最初为关闭)。该命令本身最初由 SQL 服务器执行。执行之后，提交语句本身会在每个 SQL 语句之后执行。这里 e ach 语句是一个单独的事务。

2.  **设置自动提交关闭–**
    该指令与第一条相反。执行此操作后，自动提交状态将更改为关闭。现在，用户需要在任何需要的地方明确提到提交语句。这里提交()或回滚()完成一个事务。

3.  **SET AUTOCOMMIT INT _ VALUE–**
    该指令用于限制语句的数量，语句本身由服务器自动提交。例如，在执行下面的命令后，自动提交每 9 个事务就保持打开，然后自动关闭。设置自动提交 9

4.  **SHOW AUTOCOMMIT –**
    This statement is used to determine the current status of the auto-commit so that the database users can change it according to the requirements. Hence, this statement has only two possible outcomes, either ON or OFF.

    它完全取决于数据库的类型和需要在数据库中执行的操作，即状态是保持打开还是关闭。因为如果自动提交打开，更改或修改将无法撤消。如果自动提交打开，回滚语句将不起作用。这里引入了补偿交易的概念。是的，您不能撤消更改，但是可以编写一个补偿事务来恢复数据库的先前状态。

让我们看看什么是补偿交易。

**SQL 中的补偿事务:**

补偿事务只不过是数据库操作的列表，这些操作能够撤销不完整或不一致事务的更改。补偿事务有助于恢复到数据库以前的一致状态。让我们考虑一个简单的例子。用户意外地从数据库中删除了一条重要记录。因此，补偿事务只不过是将该记录再次插入数据库。此外，补偿事务不能确保数据库初始状态的完全恢复，因为其他事务有可能同时开始执行。