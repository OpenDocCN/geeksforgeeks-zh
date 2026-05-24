# SQL | SOME

> 原文:[https://www.geeksforgeeks.org/sql-some/](https://www.geeksforgeeks.org/sql-some/)

[SQL | ALL 和 ANY](https://www.geeksforgeeks.org/sql-all-and-any/)
SOME 运算符计算外表和内表之间的条件，如果最终结果返回**任意一行**则计算为 true。如果不是，那么它的计算结果为假。

*   “某些”和“任何”比较条件彼此相似，完全可以互换。
*   有些必须与子查询中的至少一行匹配，并且必须在前面有比较运算符。

**语法:**

```sql
SELECT column_name(s)
FROM table_name
WHERE expression comparison_operator SOME (subquery) 
```

**教官表:**

| 名字 | 部门 | 薪水 |
| 钱德拉 | 计算生物学 | one |
| 维斯瓦兰 | 电子学 | One point five |
| 亚伯拉罕 | 计算机科学 | One point three |
| 约翰 | 电子学 | One point two |
| 萨曼塔 | 计算机科学 | Two |
| Jyoti | 电子学 | One point two |
| 登陆 | 计算机科学 | Two |
| 象头神。 亦称 GANAPA-TI | 计算生物学 | Zero point nine |

**示例查询和输出:**

```sql
select name
from instructor
where Salary > some(select Salary
from instructor
where dept='Computer Science');

```

**输出:**

| 维斯瓦兰 |
| 萨曼塔 |
| 登陆 |

**说明**
有工资>(某‘计算机科学’系讲师工资)的讲师获得返还。“计算机科学”系的工资是 1.3，2，2。这意味着任何工资高于 1.3 的讲师都可以包括在最终结果中。

**练习:**尝试使用 [ANY](https://www.geeksforgeeks.org/sql-all-and-any/) 子句编写相同的查询。

本文由 **Anannya Uberoi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。