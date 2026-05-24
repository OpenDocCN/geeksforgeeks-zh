# SQL LIMIT 子句

> 原文: [https://www.geeksforgeeks.org/sql-limit-clause/](https://www.geeksforgeeks.org/sql-limit-clause/)

如果有大量元组满足查询条件，那么一次只查看其中的一小部分可能是明智的。

*   `LIMIT` 子句用于设置 SQL 返回的元组数量的上限。
*   需要注意的是，并非所有的 SQL 版本都支持该子句。
*   也可以使用 SQL 2008 [`OFFSET/FETCH FIRST`](https://www.geeksforgeeks.org/sql-offset-fetch-clause/) 子句指定 `LIMIT` 子句。
*   限制/偏移表达式必须是非负整数。

**例:**
假设我们有一个关系，学生。
**学生表:**

| ROLLNO | NAME | GRADE |
| :--- | :--- | :--- |
| 10001 | Aadiya | 9 |
| 10002 | Paras | 6 |
| 10003 | Hema | 8 |
| 10004 | Robin | 9 |
| 10005 | Sita | 7 |
| 10006 | Ani | 10 |
| 10007 | Yusuf | 7 |
| 10008 | Alex | 5 |

**查询**

```sql
SELECT *
FROM Student
LIMIT 5;
```

**输出:**

| 10001 | Aadiya | 9 |
| 10002 | Paras | 6 |
| 10003 | Hema | 8 |
| 10004 | Robin | 9 |
| 10005 | Sita | 7 |

```sql
SELECT *
FROM Student
ORDER BY Grade DESC
LIMIT 3;
```

**输出:**

| 10006 | Ani | 10 |
| 10001 | Aadiya | 9 |
| 10004 | Robin | 9 |

`LIMIT` 运算符可用于上述情况，我们需要找到一个班级的前 3 名学生，并且不想使用任何条件语句。

## 使用 LIMIT 和 OFFSET

`LIMIT x OFFSET y` 仅仅意味着跳过前 `y` 个条目，然后返回下 `x` 个条目。
`OFFSET` 只能与 `ORDER BY` 子句一起使用。它不能单独使用。
偏移值必须大于或等于零。它不能为负，否则返回错误。

**查询:**

```sql
SELECT *
FROM Student
LIMIT 5 OFFSET 2
ORDER BY ROLLNO;
```

**输出:**

| 10003 | Hema | 8 |
| 10004 | Robin | 9 |
| 10005 | Sita | 7 |
| 10006 | Ani | 10 |
| 10007 | Yusuf | 7 |

## 使用 LIMIT ALL

`LIMIT ALL` 意味着没有限制。

```sql
SELECT *
FROM Student
LIMIT ALL;
```

上面的查询只返回表中的所有条目。

本文由 **Anannya Uberoi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。