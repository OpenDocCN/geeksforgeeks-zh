# SQL | ALTER(添加、删除、修改)

> 原文:[https://www.geeksforgeeks.org/sql-alter-add-drop-modify/](https://www.geeksforgeeks.org/sql-alter-add-drop-modify/)

ALTER TABLE 用于添加、删除/删除或修改现有表中的列。它还用于在现有表上添加和删除各种约束。

**更改表格–添加**

ADD 用于向现有表中添加列。有时我们可能需要添加额外的信息，在这种情况下，我们不需要再次创建整个数据库，**添加**来拯救我们。

**语法:**

```sql
 ALTER TABLE table_name
              ADD (Columnname_1  datatype,
              Columnname_2  datatype,
              …
              Columnname_n  datatype);

```

**更改表格–删除**

DROP COLUMN 用于删除表中的列。从表中删除不需要的列。

**语法:**

```sql
ALTER TABLE table_name
DROP COLUMN column_name;

```

**修改表格-修改**

它用于修改表中的现有列。也可以一次修改多个列。
**语法在不同的数据库中可能略有不同。*

**语法(Oracle、MySQL、MariaDB):**

```sql
 ALTER TABLE table_name
MODIFY column_name column_type;

```

**语法(SQL Server):**

```sql
 ALTER TABLE table_name
ALTER COLUMN column_name column_type; 

```

**查询** 

**样表:**

**学生**

| **滚动 _ 否** | **名称** |
| --- | --- |
| one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) |
| Two | Abhi |
| three | Rahul |
| four | 塔努 |

**查询:**

*   向学生表中添加 2 列年龄和课程。

```sql
 ALTER TABLE Student ADD (AGE number(3),COURSE varchar(40));
```

**输出:**

| **滚动 _ 否** | **名称** | **年龄** | **课程** |
| --- | --- | --- | --- |
| one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) |  |  |
| Two | Abhi |  |  |
| three | Rahul |  |  |
| four | 塔努 |  |  |

*   修改学生表中的课程列

```sql
 ALTER TABLE Student MODIFY COURSE varchar(20); 
```

运行上述查询后，课程栏的最大大小从 40 减小到 20。

*   在学生表中删除课程列。

```sql
 ALTER TABLE Student DROP COLUMN COURSE;
```

**输出:**

| **滚动 _ 否** | **名称** | **年龄** |
| --- | --- | --- |
| one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) |  |
| Two | Abhi |  |
| three | Rahul |  |
| four | 塔努 |  |

本文由 **Shubham Chaudhary** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。