# SQL | INSERT IGNORE 语句

> 原文:[https://www.geeksforgeeks.org/sql-insert-ignore-statement/](https://www.geeksforgeeks.org/sql-insert-ignore-statement/)

我们知道表的主键不能重复。例如，学生表中的学生人数必须始终不同。同样，雇员标识在雇员表中应该是唯一的。当我们试图在重复主键的表中插入元组时，会导致错误。但是，使用 INSERT IGNORE 语句，我们可以防止这种错误出现，尤其是在批量插入条目时，这种错误会中断插入流程。相反，只会生成警告。

**插入忽略避免错误的情况**

*   在列必须包含主键或唯一约束的情况下插入重复键时
*   在列具有非空约束的情况下插入空值时。
*   将行插入分区表时，插入的值与分区格式相反。

**示例:**

假设我们有关系，员工。

**员工表:**

| 员工 ID | 名字 | 城市 |
| Fifteen thousand and one | 阿卡巴 | 德里 |
| Fifteen thousand and three | 在海滩上 | 班加罗尔 |
| Fifteen thousand and ten | 约翰 | 海得拉巴 |
| Fifteen thousand and eight | 雪莱 | 德里 |
| Fifteen thousand and two | Ananya | 孟买 |
| Fifteen thousand and four | 希雅·凯特·伊索贝尔·富勒 | 浦那 |

正如我们所注意到的，条目不是根据它们的主键(即 EmployeeID)进行排序的。

**样本查询:**

```sql
INSERT IGNORE INTO Employee (EmployeeID, Name, City)
VALUES (15002, 'Ram', 'Mumbai');

```

**输出:**
未插入条目。

**样本查询:**

**插入多条记录**

一次插入多条记录时，任何不能插入的记录都不会被插入，但任何可以插入的记录都会被插入:

```sql
INSERT IGNORE INTO Employee (EmployeeID, Name, City)
VALUES (15007, 'Shikha', 'Delhi'), (15002, 'Ram', 'Mumbai'), (15009, 'Sam', 'Ahmedabad');

```

**输出:**
第一个和最后一个条目被插入；中间的条目被简单忽略。不会出现错误。

**劣势**

大多数用户不喜欢插入忽略而不喜欢插入，因为有些错误可能会被忽略。这可能会导致表中的不一致，从而导致一些元组在用户没有机会纠正它们的情况下无法插入。因此，必须在非常特殊的条件下使用 INSERT IGNORE。

本文由 **Anannya Uberoi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。