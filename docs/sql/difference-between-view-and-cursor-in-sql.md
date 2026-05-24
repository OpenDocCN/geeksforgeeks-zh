# SQL 中视图和光标的区别

> 原文:[https://www . geesforgeks . org/SQL 中视图和光标的区别/](https://www.geeksforgeeks.org/difference-between-view-and-cursor-in-sql/)

**1。** [**视图**](https://www.geeksforgeeks.org/sql-views/) **:**
视图是一个虚拟表，它实际上不存在于数据库中，但可以根据特定用户的请求生成。视图是一个对象，它为用户提供了基表数据的逻辑视图，我们可以通过允许用户查看表中唯一必要的列并隐藏其他数据库详细信息来限制用户可以查看的内容。视图还允许用户根据自己的需求访问数据，因此不同的用户可以根据自己的需求以不同的方式访问相同的数据。

**2。** [**光标**](https://www.geeksforgeeks.org/cursors-in-pl-sql/) **:**
光标是在内存中创建的临时工作区，用于在执行 SQL 语句时处理和存储与该语句相关的信息。临时工作区用于存储从数据库中检索的数据，并根据需要操作数据。它包含了 select 语句访问数据的所有必要信息。它可以保存一组称为活动集的行，但一次只能访问一行。有两种不同类型的光标–
1。隐式光标
2。显式光标

**SQL 中视图与光标的区别:**

<figure class="table">

| s No. | view | cursor |
| --- | --- | --- |
| 1。 | A view is a virtual table, which gives a logical view of the base table data. | Cursor is a temporary workstation created in the database server when SQL statements are executed. |
| 2。 | The view is dynamic in nature, which means that any changes made in the base table are immediately reflected in the view. | The cursor can be static or dynamic. |
| 3。 | We can perform CRUD operations on views, such as creating, inserting, deleting and updating. | 创建显式光标有一些步骤–

*   Declare the cursor in the declaration section.
*   Open the cursor in the execution section.
*   Take the cursor to retrieve the data into PL/SQL variables.
*   Close the cursor to release the allocated memory.

 |
| 4。 | There are two types of views [](https://www.geeksforgeeks.org/difference-between-simple-and-complex-view-in-sql/), namely simple views (created from a single table) and complex cursors (created from multiple tables). | There are two types of cursors, namely implicit cursors (predefined) and explicit cursors (user-defined). |
| 5。 | A view is a database object similar to a table, so it can be used for both SQL and PL/SQL. | Cursor is defined and used in stored procedure block, which means it can only be used in PL/SQL. |
| 6。 | General syntax for creating views:
Create the view "VIEW_NAME" as "SQL statement";
 | 创建视图的一般语法:
CURSOR _ name IS select _ statement；
 |

</figure>