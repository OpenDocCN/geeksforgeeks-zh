# SQL |唯一约束

> 原文:[https://www.geeksforgeeks.org/sql-unique-constraint/](https://www.geeksforgeeks.org/sql-unique-constraint/)

[SQL 约束](https://www.geeksforgeeks.org/sql-constraints/)

SQL 中的唯一约束用于检查子查询的结果中是否有重复的元组。它返回一个布尔值，指示重复元组的存在/不存在。唯一构造只有在子查询没有重复元组时才返回 true，否则返回 false。

**要点:**

*   对空子查询的计算结果为真。
*   仅当存在作为子查询输出的唯一元组时返回 true(如果两个元组的任何属性值不同，则两个元组是唯一的)。
*   如果子查询有两个重复行，并且至少有一个属性为空，则返回 true。

**语法:**

```sql
SELECT table.ID
FROM  table
WHERE UNIQUE (SELECT table2.ID
              FROM table2
              WHERE table.ID = table2.ID);

```

**注意:**在执行过程中，首先对外部查询进行求值，以获得 table.ID。随后，处理内部子查询，该子查询生成一个新的关系，该关系包含该表等内部查询的输出。如果新关系中的每一行都是唯一的，那么 unique 返回 true，对应的表也是唯一的。ID 作为元组添加到生成的输出关系中。但是，如果新关系中的每一行都不是唯一的，那么 unique 的计算结果为 false，相应的表也是如此。标识没有添加到输出关系中。

当且仅当存在两个元组 t1 和 t2，使得 t1 = t2 时，应用于子查询的 Unique 返回 false。当 unique 被应用于包含 t1 和 t2 的子查询，使得 t1 = t2 并且这些元组的至少一个属性包含空值时，它认为 t1 和 t2 是两个不同的元组。在这种情况下，唯一谓词的计算结果为 true。这是因为，SQL 中的空值被视为未知值，因此，两个空值被认为是不同的。

**注意:**不带 UNIQUE 子句的 SQL 语句也可以写成:

```sql
SELECT table.ID
FROM  table
WHERE 1 <= (SELECT count(table2.ID)
              FROM table2
              WHERE table.ID = table2.ID);
```

**查询**

**例 1:** 找出 2017 年最多教过一门课的所有导师。
**教官** **关系:**

| 员工 ID | 名字 | 快跑！快跑 | 年 |
| Seventy-seven thousand five hundred and five | 艾伦 | SC110 | Two thousand and seventeen |
| Seventy-seven thousand eight hundred and fifteen | 威尔(男子名) | CSE774 | Two thousand and seventeen |
| Eighty-five thousand and nineteen | 史密斯（姓氏） | EE457 | Two thousand and seventeen |
| Ninety-two thousand seven hundred and one | 萨姆（男子名） | PYS504 | Two thousand and seventeen |
| Sixty thousand two hundred and fifteen | 哈罗德 | HSS103 | Two thousand and sixteen |
| Seventy-seven thousand five hundred and five | 艾伦 | BIO775 | Two thousand and seventeen |
| Ninety-two thousand seven hundred and one | 萨姆（男子名） | ECO980 | Two thousand and seventeen |

```sql
SELECT I.EMPLOYEEID, I.NAME
FROM Instructor as I
WHERE UNIQUE (SELECT Inst.EMPLOYEEID
              FROM Instructor as Inst
              WHERE I.EMPLOYEEID = Inst.EMPLOYEEID
                          and Inst.YEAR = 2017);
```

**输出:**

| 员工 ID | 名字 |
| Seventy-seven thousand eight hundred and fifteen | 威尔(男子名) |
| Eighty-five thousand and nineteen | 史密斯（姓氏） |

**说明:**在讲师关系中，2017 年期间只有讲师威尔和史密斯教授一门课程。对应于这些指导者的子查询仅包含单元组，因此对应于这些指导者的唯一子句评估为真，从而在输出关系中产生这两个指导者。

* * *

**示例 2:** 查找计算机科学系中只有一名教师分配到该课程的所有课程。
T3】航线关系:

| 快跑！快跑 | 名字 | 部门 | 说明 ID |
| CSE505 | 计算机网络 | 计算机科学 | Eleven thousand and seventy-one |
| CSE245 | 操作系统 | 计算机科学 | Seventy-four thousand five hundred and five |
| CSE101 | 编程；编排 | 计算机科学 | Twelve thousand seven hundred and fifteen |
| HSS505 | 心理学 | 社会科学 | Eighty-five thousand and seventeen |
| EE475 | 信号与系统 | 与电有关的 | Twenty-two thousand one hundred and fifty |
| CSE314 | 数据库管理系统 | 计算机科学 | Forty-four thousand seven hundred and four |
| CSE505 | 计算机网络 | 计算机科学 | Eleven thousand seven hundred and forty-seven |
| CSE314 | 数据库管理系统 | 计算机科学 | Forty-four thousand seven hundred and fifteen |

```sql
SELECT C.COURSEID, C.NAME
FROM Course as C
WHERE UNIQUE (SELECT T.INSTRUCTORID
              FROM Course as T
              WHERE T.COURSEID = C.COURSEID 
                          and C.DEPARTMENT = 'Computer Science');
```

**输出:**

| 快跑！快跑 | 名字 |
| CSE245 | 操作系统 |
| CSE101 | 编程；编排 |

**说明:**在课程关系中，计算机科学系唯一分配到一名讲师的课程是操作系统和编程。对应于这两门课程的唯一约束只有一个由相应教师组成的元组。因此，这两个课程的唯一子句评估为真，并且这些课程以输出关系显示。课程关系中的其他课程要么有两个或更多的讲师，要么不属于计算机科学系，因此这些课程不会显示在输出关系中。

本文由 **Mayank Kumar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。