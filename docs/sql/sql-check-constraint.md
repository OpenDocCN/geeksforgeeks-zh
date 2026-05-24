# SQL |检查约束

> 原文:[https://www.geeksforgeeks.org/sql-check-constraint/](https://www.geeksforgeeks.org/sql-check-constraint/)

[SQL 约束](https://www.geeksforgeeks.org/sql-constraints/)
检查约束用于指定给定关系中每个元组必须满足的谓词。它限制了列在关系中可以容纳的值。

*   check 约束中的谓词可以保存子查询。
*   在属性上定义的检查约束限制了该属性的值范围。
*   如果添加到元组属性的值违反了检查约束，则检查约束的计算结果为 false，相应的更新被中止。
*   检查约束通常用 SQL 中的 CREATE TABLE 命令指定。

**语法:**

```sql
CREATE TABLE pets(
        ID INT NOT NULL,
        Name VARCHAR(30) NOT NULL,
        Breed VARCHAR(20) NOT NULL,
        Age INT,
        GENDER VARCHAR(9),
        PRIMARY KEY(ID),
        check(GENDER in ('Male', 'Female', 'Unknown'))
        );
```

**注意:**上述 SQL 命令中的检查约束将 GENDER 限制为只属于指定的类别。如果添加了一个新的元组，或者用不属于上述三个类别中任何一个的性别更新了关系中的一个现有元组，那么相应的数据库更新将被中止。

**查询**

限制条件:只有年龄≥17 岁的学生才能报读大学。
**大学学生数据库模式:**

```sql
CREATE TABLE student(
        StudentID INT NOT NULL,
        Name VARCHAR(30) NOT NULL,
        Age INT NOT NULL,
        GENDER VARCHAR(9),
        PRIMARY KEY(ID),
        check(Age >= 17)
        );
```

**学生关系:**

| 学生证 | 名字 | 年龄 | 性别 |
| One thousand and one | 留宿（remain overnight 的缩写） | Eighteen | 男性的 |
| One thousand and two | 萨姆（男子名） | Seventeen | 男性的 |
| One thousand and three | 格鲁吉亚 | Seventeen | 女性的 |
| One thousand and four | 埃里克 | Nineteen | 未知的 |
| One thousand and five | 克里斯廷 | Seventeen | 女性的 |

**说明:**在上述关系中，根据关系的图式中 check 语句提到的约束，所有学生的年龄都大于等于 17 岁。但是，如果执行了以下 SQL 语句:

```sql
INSERT INTO student(STUDENTID, NAME, AGE, GENDER) 
VALUES (1006, 'Emma', 16, 'Female');
```

不会有任何数据库更新，因为年龄< 17 岁。

**使用检查约束的不同选项:** 

*   **使用 alter:** 检查约束也可以使用语法:

    ```sql
    alter table TABLE_NAME modify COLUMN_NAME check(Predicate);
    ```

    添加到已经创建的关系中
*   **为检查约束赋予变量名:**检查约束可以使用以下语法赋予变量名:

    ```sql
    alter table TABLE_NAME add constraint CHECK_CONST check (Predicate);
    ```

*   **删除检查约束:**可以使用语法:

    ```sql
    alter table TABLE_NAME drop constraint CHECK_CONSTRAINT_NAME;
    ```

    从 SQL server 的数据库关系中删除检查约束
*   **删除检查约束:**可以使用语法:

    ```sql
    alter table TABLE_NAME drop check CHECK_CONSTRAINT_NAME;
    ```

    从 MySQL 数据库中的关系中删除检查约束

本文由 **Mayank Kumar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。