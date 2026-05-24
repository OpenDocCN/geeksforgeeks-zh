# SQL DISTINCT 子句

> 原文: [https://www.geeksforgeeks.org/sql-distinct-clause/](https://www.geeksforgeeks.org/sql-distinct-clause/)

`DISTINCT` 关键字与 `SELECT` 关键字结合使用。当需要避免任何特定列/表中出现重复值时，这很有帮助。当我们使用 `DISTINCT` 关键字时，只获取**唯一值**。

## 语法

```sql
SELECT DISTINCT column1, column2 
FROM table_name;
```

- `column1`, `column2`: 表中字段的名称。
- `table_name`: 我们要从中获取记录的表。

该查询将返回表中具有字段 `column1`、`column2` 的行的所有唯一组合。

**注意:** 如果 `DISTINCT` 关键字用于多列，则在结果集中显示 `DISTINCT` 组合。

## 示例

假设有一个名为 `Student` 的表，数据如下：

| Roll_No | Name   | Address | Delhi | XXXXXX |
| :------ | :----- | :------ | :---- | :----- |
| 1       | SURESH | -       | -     | -      |
| 2       | SUJIT  | -       | -     | -      |
| 3       | RAM    | -       | -     | -      |
| 4       | RAM    | -       | -     | -      |
| 5       | SURESH | -       | -     | -      |
| 6       | SUJIT  | -       | -     | -      |

### 查询 1

从 `Name` 字段提取唯一名称：

```sql
SELECT DISTINCT Name 
FROM Student;
```

**输出:**

| Name   |
| :----- |
| SURESH |
| SUJIT  |
| RAM    |

### 查询 2

从整个表中获取唯一的行组合：

```sql
SELECT DISTINCT * 
FROM Student;
```

**输出:**

| **Roll_No** | **Name** | **Address** | **Delhi** | **XXXXXX** |
| :---------- | :------- | :---------- | :-------- | :--------- |
| 1           | SURESH   | -           | -         | -          |
| 2           | SUJIT    | -           | -         | -          |
| 3           | RAM      | -           | -         | -          |

**注意:** 在上述两个示例中，如果没有 `DISTINCT` 关键字，将会获取 6 条记录，而不是 4 条，因为在原始表中有 6 条记录具有重复值。

***

本文由 [**哈什·阿加瓦尔**](https://www.facebook.com/harsh.agarwal.16752) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。