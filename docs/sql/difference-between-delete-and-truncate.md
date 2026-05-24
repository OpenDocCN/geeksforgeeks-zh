# 删除和截断的区别

> 原文:[https://www . geesforgeks . org/delete-and-truncate 之差/](https://www.geeksforgeeks.org/difference-between-delete-and-truncate/)

**1。DELETE :**
DELETE 是一个 [DML(数据操作语言)](https://www.geeksforgeeks.org/difference-between-ddl-and-dml-in-dbms/)命令，在我们指定要从表或关系中删除的行(元组)时使用。DELETE 命令可以包含一个 WHERE 子句。如果 **WHERE** 子句与 DELETE 命令一起使用，那么它只删除或删除那些满足条件的行(元组)，否则默认情况下，它从表中删除所有元组(行)。

**DELETE 命令语法:**

```sql
DELETE FROM TableName 
WHERE condition; 
```

**2。TRUNCATE :**
TRUNCATE 是一个 [DDL(数据定义语言)](https://www.geeksforgeeks.org/difference-between-ddl-and-dml-in-dbms/)命令，用于删除表中的所有行或元组。与 DELETE 命令不同，TRUNCATE 命令不包含 WHERE 子句。在 TRUNCATE 命令中，会记录每个已删除数据页的事务日志。与 DELETE 命令不同，TRUNCATE 命令速度很快。在使用 TRUNCATE 命令后，我们无法回滚数据。

**TRUNCATE 命令的语法:-**

```sql
TRUNCATE TABLE  TableName; 
```

让我们看看 DELETE 和 TRUNCATE 命令之间的区别:-

<figure class="table">

| S.NO | delete | cut off |
| --- | --- | --- |
| 1。 | The DELETE command is used to delete a specified row (one or more rows). | This command is used to delete all rows in the table. |
| 2。 | Is a DML (data manipulation language) command. | Although it is a DDL (Data Definition Language) command. |
| 3。 | In order to filter records, there may be a WHERE clause in the DELETE command. | There may be no WHERE clause in TRUNCATE command. |
| 4。 | In the DELETE command, a tuple is locked before being removed. | In this command, the data page is locked before the table data is removed. |
| 5。 | DELETE statement deletes one row at a time and records an entry in the transaction log for each deleted row. | TRUNCATE TABLE removes data by deallocating data pages used to store table data, and only the page deallocation is recorded in the transaction log. |
| 6。 | The DELETE command is slower than the TRUNCATE command. | The TRUNCATE command is faster than the DELETE command. |
| 7。 | To use delete, you need to have delete permission on the table. | To use Truncate on a table, we need at least ALTER permission on the table. |
| 8。 | After using the DELETE statement in the table, the identity of the column retains the identity. | If the table contains an identity column, the identity of the column will be reset to its seed value. |
| 9。 | Delete view that can be used for index. | Truncate cannot be used for indexed views. |

</figure>