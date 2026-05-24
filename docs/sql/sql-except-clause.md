# SQL |除外条款

> 原文:[https://www.geeksforgeeks.org/sql-except-clause/](https://www.geeksforgeeks.org/sql-except-clause/)

在 SQL 中，EXCEPT 返回那些由第一个 SELECT 操作返回的元组，而不是由第二个 SELECT 操作返回的元组。

这与在关系代数中使用减法运算符相同。

**例:**
说我们有两个关系，学生和 TA(助教)。我们想把那些不是助教的学生都退回去。该查询可以表述为:

**学生表:**

| 学生证 | 名字 | 课程 |
| one | 罗汉 | 数据库管理系统 |
| Two | 凯文 | 操作系统（Operating System） |
| three | 曼西 | 数据库管理系统 |
| four | 曼西 | 自动数据采集（Automaticdataacquisitions） |
| five | 雷卡 | 自动数据采集（Automaticdataacquisitions） |
| six | 非常 | 操作系统（Operating System） |

| 学生证 | 名字 | Course

**TA 表:** 

 |
| one | 凯文 | 火车运行公司 |
| Two | 悉多 | 互联网协议(Internet Protocol) |
| three | 马尼克 | 美国联合通讯社(Associated Press) |
| four | 雷卡 | 社交网站（Social Network Site 的缩写） |

```sql
SELECT Name
       FROM Students
EXCEPT
SELECT NAME
       FROM TA;

```

**输出:**

```sql
Rohan
Mansi
Megha

```

要保留重复项，我们必须明确地写**excepall**而不是 EXCEPT。

```sql
SELECT Name
       FROM Students
EXCEPTALL
SELECT Name
       FROM TA;

```

**输出:**

```sql
Rohan
Mansi
Mansi
Megha

```

**EXCEPT 和 NOT IN 子句的区别**
EXCEPT 会自动移除最终结果中的所有重复项，而 NOT IN 会保留重复的元组。还需要注意的是，MySQL 不支持 EXCEPT。

本文由 **Anannya Uberoi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。