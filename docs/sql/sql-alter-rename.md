# SQL | ALTER (RENAME)

> 原文:[https://www.geeksforgeeks.org/sql-alter-rename/](https://www.geeksforgeeks.org/sql-alter-rename/)

有时，我们可能想要重命名我们的表，给它一个更相关的名称。为此，我们可以使用**改变表**来重命名表的名称。

**语法在不同的数据库中可能有所不同。*

**语法(Oracle、MySQL、MariaDB):**

```sql
ALTER TABLE table_name
RENAME TO new_table_name;
```

也可以使用**改变表格**给列赋予新的名称。

**语法(MySQL，Oracle):**

```sql
ALTER TABLE table_name
RENAME COLUMN old_name TO new_name;
```

**语法(MariaDB):**

```sql
ALTER TABLE table_name
CHANGE COLUMN old_name TO new_name;
```

**样表:**
学生

<figure class="table">**【roll _ no】**

| name |
| --- |

</figure>

**查询:**

*   将学生表中的列名更改为名字。

```sql
ALTER TABLE Student RENAME COLUMN NAME TO FIRST_NAME;
```

**输出:**

<figure class="table">

| **【滚 _ 号】** | **【名 _ 名】** |

</figure>

*   将学生表的名称更改为学生详细信息

```sql
ALTER TABLE Student RENAME TO Student_Details;
```

**输出:**
【学生 _ 详细资料】
**【t1 _ name】**

| **【滚 _ 号】** |
| --- |

本文由 **Shubham Chaudhary** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。