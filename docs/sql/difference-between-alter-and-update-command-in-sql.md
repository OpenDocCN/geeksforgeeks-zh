# SQL 中 ALTER 和 UPDATE 命令的区别

> 原文:[https://www . geesforgeks . org/alter-and-update-command-in-SQL/](https://www.geeksforgeeks.org/difference-between-alter-and-update-command-in-sql/)之间的差异

**1。更改命令:**

ALTER SQL 命令是一个 DDL(数据定义语言)语句。ALTER 用于更新数据库中表的结构(如添加、删除、修改数据库中表的属性)。

**语法:**

```sql
// add a column to the existing table

ALTER TABLE tableName

ADD columnName columnDefinition;

// drop a column from the existing table

ALTER TABLE tableName

DROP COLUMN columnName;

// rename a column in the existing table

ALTER TABLE tableName

RENAME COLUMN olderName TO newName;

// modify the datatype of an already existing column in the table

ALTER TABLE table_name

ALTER COLUMN column_name column_type;

```

**2。更新命令:**

更新命令是一个数据操作语言语句。它用于操作任何现有列的数据。但是不能被改变表的定义。

**语法:**

```sql
// table name that has to update

UPDATE tableName

// which columns have to update

SET column1 = value1, column2 = value2, ...,columnN=valueN.

// which row you have to update

WHERE condition

```

注意:如果没有 WHERE 子句，表中的所有记录都将被更新。

**SQL 中 ALTER 和 UPDATE 命令的区别:**

<figure class="table">

| -你好。不，不 | ALTER command | 更新命令 |
| --- | --- | --- |
| one | The ALTER command is data definition language (DDL). | Update command is a data manipulation language. |
| Two | The Alter command will perform actions at the structure level instead of the data level. | The update command will be executed at the data level. |
| three | Command is used to add, delete and modify the attributes of relationships (tables) in the database. | The UPDATE command is used to update the existing records in the database. |
| four | Command initializes the values of all tuples to NULL by default. | The update command sets the value specified in the command to the tuple. |
| five | This command changes the table structure. | This command modifies the data in the table. |
| six | Example: table structure, table name, SP, function, etc. | Example: Change data rows or columns in a table, etc. |

</figure>