# 删除、删除和截断的区别

> 原文:[https://www . geesforgeks . org/delete-drop-and-truncate 之差/](https://www.geeksforgeeks.org/difference-between-delete-drop-and-truncate/)

**1。删除:**
基本上是[数据操纵语言命令(DML)](https://www.geeksforgeeks.org/sql-ddl-dql-dml-dcl-tcl-commands/) 。它用于删除表中的一个或多个元组。在“DELETE”命令的帮助下，我们可以一次删除所有行，也可以一行一行地删除。也就是说，我们可以根据使用 Where 子句的要求或条件使用它。它比 TRUNCATE cmd 相对慢。

*   **语法–**
    如果我们想删除表中的所有行:

    ```sql
    DELETE from ; 
    ```

*   **语法–**
    如果我们想根据条件删除表中的行，那么我们使用 WHERE 子句，

    ```sql
    DELETE from WHERE  <condition>;</condition> 
    ```

**注意–**
这里我们可以使用“ROLLBACK”命令来恢复元组。

**2。降:**
这是一个数据定义语言命令(DDL)。它用来放下整个桌子。在“DROP”命令的帮助下，我们可以一次性删除整个结构，也就是说，它删除了模式的命名元素。通过使用这个命令，整个表的存在就结束了，或者说丢失了。

*   **语法–**
    如果我们想取消表格:

    ```sql
    DROP table ; 
    ```

**注意–**
这里我们不能使用“ROLLBACK”命令恢复表。

**3。TRUNCATE :**
也是数据定义语言命令(DDL)。它用于一次性删除关系(表)的所有行。在“TRUNCATE”命令的帮助下，我们不能删除单行，因为这里没有使用 WHERE 子句。使用此命令，表中所有行的存在都将丢失。它比 delete 命令相对更快，因为它会快速删除所有行。

*   **语法–**
    如果我们想使用截断:

    ```sql
    TRUNCATE  ; 
    ```

**注意–**
这里我们不能使用“ROLLBACK”命令恢复表的元组。