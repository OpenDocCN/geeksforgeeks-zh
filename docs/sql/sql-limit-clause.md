# SQL |限制条款

> 原文:[https://www.geeksforgeeks.org/sql-limit-clause/](https://www.geeksforgeeks.org/sql-limit-clause/)

如果有大量元组满足查询条件，那么一次只查看其中的一小部分可能是明智的。

*   LIMIT 子句用于设置 SQL 返回的元组数量的上限。
*   需要注意的是，并非所有的 SQL 版本都支持该子句。
*   也可以使用 SQL 2008[OFFSET/FETCH FIRST](https://www.geeksforgeeks.org/sql-offset-fetch-clause/)子句指定 LIMIT 子句。
*   限制/偏移表达式必须是非负整数。

**例:**
说我们有关系，学生。
**学生表:**

| 罗龙 | 名字 | 级别 |
| Twelve thousand and one | 阿迪亚 | nine |
| Twelve thousand and two | 在海滩上 | six |
| Twelve thousand and three | Hema | eight |
| Twelve thousand and four | 知更鸟 | nine |
| Twelve thousand and five | 悉多 | seven |
| Twelve thousand and six | 安妮 | Ten |
| Twelve thousand and seven | 优素福 | seven |
| Twelve thousand and eight | 亚历克斯 | five |

**查询**

```sql
SELECT *
FROM Student
LIMIT 5;

```

**输出:**

| Twelve thousand and one | 阿迪亚 | nine |
| Twelve thousand and two | 在海滩上 | six |
| Twelve thousand and three | Hema | eight |
| Twelve thousand and four | 知更鸟 | nine |
| Twelve thousand and five | 悉多 | seven |

```sql
SELECT *
FROM Student
ORDER BY Grade DESC
LIMIT 3;

```

**输出:**

| Twelve thousand and six | 安妮 | Ten |
| Twelve thousand and one | 阿迪亚 | nine |
| Twelve thousand and four | 知更鸟 | nine |

LIMIT 运算符可用于上述情况，我们需要找到一个班级的前 3 名学生，并且不想使用任何条件语句。

**使用极限和偏移**

LIMIT x OFFSET y 仅仅意味着跳过前 y 个条目，然后返回下 x 个条目。
OFFSET 只能与 ORDER BY 子句一起使用。它不能单独使用。
偏移值必须大于或等于零。它不能为负，否则返回错误。
T3】查询:

```sql
SELECT *
FROM Student
LIMIT 5 OFFSET 2
ORDER BY ROLLNO;

```

**输出:**

| Twelve thousand and three | Hema | eight |
| Twelve thousand and four | 知更鸟 | nine |
| Twelve thousand and five | 悉多 | seven |
| Twelve thousand and six | 安妮 | Ten |
| Twelve thousand and seven | 优素福 | seven |

**使用全部限制**

限制所有意味着没有限制。

```sql
SELECT *
FROM Student
LIMIT ALL;

```

上面的查询只返回表中的所有条目。

本文由 **Anannya Uberoi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。