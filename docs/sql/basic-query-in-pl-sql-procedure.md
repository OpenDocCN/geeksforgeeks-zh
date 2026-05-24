# PL/SQL 程序中的基本查询

> 原文:[https://www . geesforgeks . org/basic-query-in-pl-SQL-procedure/](https://www.geeksforgeeks.org/basic-query-in-pl-sql-procedure/)

在本文中，我们将讨论 PL/SQL 的概述，然后主要讨论在 PL/SQL 中执行基本的查询操作。最后将以 PL/ SQL 子程序中的参数模式结束。我们一个一个来讨论。

**简介:**
[PL/SQL](https://www.geeksforgeeks.org/plsql-introduction/) 代表对 SQL 的过程语言扩展。在过程中，子程序的作用是执行特定的任务，它是程序的一个单元模块。它组合起来形成更大的程序。子程序可以被另一个叫做调用程序的程序所包含。PL/SQL 提供了可执行单元代码的块结构。它提供过程构造，例如，在控制结构中包括循环、条件语句和变量、常量和数据类型。

**特性:**
它可以在模式级别、包内部和 PL /SQL 块内部创建。

1.  模式级子程序是一个独立的子程序。它是用 CREATE PROCEDURE 语句创建的。在子程序中，它存储在数据库中，可以用 DROP PROCEDURE 语句删除。
2.  它存储在数据库中，并且使用 DROP PACKAGE 语句删除该包。
3.  PL/SQL 提供了一种子程序函数和程序。

**PL /SQL 中的函数和过程:**
下面我们来理解一下 PL/SQL 中函数和过程的含义。

1.  **函数–**
    用单个值写。它用于计算和返回值。

2.  **程序–**
    主要用来执行一个动作。

**在 PL/SQL 中创建过程:**
在这里，我们将讨论如何使用 PL/SQL 查询创建过程，如下所示。

**语法–**

```sql
CREATE [ OR REPLACE ] PROCEDURE 
procedure_name 
[( Parameter [ parameter ] ) ] 
IS 
[ declaration_section ] 
BEGIN 
executable_section 
[ EXCEPTION 
exception_section] 
END [ procedure_name]; 
```

**删除 PL/SQL 中的过程:**
一旦我们在 Oracle 中创建了一个过程，我们需要使用 DROP 命令将其从数据库中删除，如下所示。

**语法–**

```sql
DROP PROCEDURE procedure_name; 
```

**示例–**

```sql
DROP PROCEDURE Update course; 
```

**PL/ SQL 子程序中的参数模式:**
在这里，我们将对 PL/SQL 子程序中的参数模式进行如下讨论。

1.  **IN–**
    它是只读参数。输入参数就像一个常数。在被调用的程序或函数中，它可以被引用。程序无法为输入参数指定新值。它们的值不能在子程序中更改。

2.  **OUT–**
    用于获取子程序输出。它是子程序中的读写变量。它们的值可以在子程序中更改。

3.  **输入输出–**
    从子程序中获取输入输出，然后这个输入输出可以用来获取结果。它们的值可以在子程序中更改。