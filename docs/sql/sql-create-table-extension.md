# SQL |创建表扩展

> 原文:[https://www.geeksforgeeks.org/sql-create-table-extension/](https://www.geeksforgeeks.org/sql-create-table-extension/)

SQL 为 **[CREATE TABLE](https://www.geeksforgeeks.org/sql-create/)** 子句提供了扩展，该子句使用数据库中某个现有表的相同模式创建一个新表。

*   它用于将复杂查询的结果临时存储在新表中。
*   创建的新表与引用表具有相同的模式。
*   默认情况下，新表具有与引用表相同的列名和数据类型。

**语法:**

```sql
CREATE TABLE newTable LIKE pets
```

**示例:**

```sql
CREATE TABLE newTable as
            (SELECT * 
             FROM pets
             WHERE pets.BREED = 'German Shepherd')

```

**查询**

**宠物桌:**

| 身份证明 | 名字 | 类型 | 性别 |
| Eleven thousand four hundred and forty-one | 英国列兵 | 德国牧羊犬 | 男性的 |
| Eleven thousand four hundred and forty-two | 最大 | 短毛小猎犬 | 男性的 |
| Eleven thousand four hundred and forty-three | 傻瓜 | 哈巴狗 | 男性的 |
| Eleven thousand four hundred and forty-four | 雏菊 | 狮子狗 | 女性的 |
| Eleven thousand four hundred and forty-five | 佐伊 | 拉布拉多 | 女性的 |
| Eleven thousand four hundred and forty-six | 托比 | 斗牛犬 | 男性的 |

 **查询 1:**

```sql
CREATE TABLE newTable LIKE pets;
SELECT * 
FROM newTable 
where newTable.GENDER = 'Female';
```

**输出:**

| 身份证明 | 名字 | 类型 | 性别 |
| Eleven thousand four hundred and forty-four | 雏菊 | 狮子狗 | 女性的 |
| Eleven thousand four hundred and forty-five | 佐伊 | 拉布拉多 | 女性的 |

**说明:**创建的 newTable 是宠物表的副本。因此，从 newTable 中选择雌性宠物只会返回两行，其中宠物是雌性。
T3】查询 2 :

```sql
CREATE TABLE newTable as
            (SELECT * 
             FROM pets
             WHERE pets.BREED = 'German Shepherd');
SELECT * from newTable;

```

**输出:**

| 身份证明 | 名字 | 类型 | 性别 |
| Eleven thousand four hundred and forty-one | 英国列兵 | 德国牧羊犬 | 男性的 |

**说明:**首先对内部查询进行求值，并将结果存储在一个新的临时关系中。接下来，评估外部查询，创建新表，并将内部查询的输出添加到新表中。

**参考文献:**数据库系统概念第 6 版

本文由 **Mayank Kumar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。