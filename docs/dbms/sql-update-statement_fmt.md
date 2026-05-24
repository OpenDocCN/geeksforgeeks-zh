# SQL UPDATE 语句

> 原文：[https://www.geeksforgeeks.org/sql-update-statement/](https://www.geeksforgeeks.org/sql-update-statement/)

SQL 中的 `UPDATE` 语句用于更新数据库中现有表的数据。根据我们的需求，我们可以使用 `UPDATE` 语句更新单个列和多个列。

## 基本语法

```sql
UPDATE table_name SET column1 = value1, column2 = value2,... 
WHERE condition;
```

- `table_name`：表的名称。
- `column1`：第一、第二、第三列的名称……
- `value1`：第一、第二、第三列的新值……
- `condition`：用于选择需要更新列值的行的条件。

**注意：** 在上面的查询中，`SET` 语句用于为特定列设置新值，`WHERE` 子句用于选择需要更新列的行。如果我们没有使用 `WHERE` 子句，那么所有行的列都将被更新。所以 `WHERE` 子句用于选择特定的行。

[![table1](img/4fab6fceee0b1d1b256c3430eb713844.png)](https://media.geeksforgeeks.org/wp-content/cdn-uploads/table11.jpg)

## 示例查询

### 更新单个列

更新 `NAME` 列，并在所有 `Age` 为 20 的行中将值设置为 ‘PRATIK’。

```sql
UPDATE Student SET NAME = 'PRATIK' WHERE Age = 20;
```

**输出：**
该查询将更新两行（第三行和第五行），表 `Student` 现在看起来像：

| ROLL_NO | NAME | ADDRESS | PHONE | AGE |
| :--- | :--- | :--- | :--- | :--- |
| 1 | RAM | DELHI | XXXXXXXXXX | 18 |
| 2 | RAMESH | GURGAON | XXXXXXXXXX | 18 |
| 3 | PRATIK | ROHTAK | XXXXXXXXXX | 20 |
| 4 | SURESH | DELHI | XXXXXXXXXX | 18 |
| 5 | PRATIK | ROHTAK | XXXXXXXXXX | 20 |
| 6 | RAMESH | GURGAON | XXXXXXXXXX | 18 |

### 更新多个列

将 `NAME` 更新为 ‘PRATIK’，`ADDRESS` 更新为 ‘SIKKIM’，其中 `ROLL_NO` 为 1。

```sql
UPDATE Student SET NAME = 'PRATIK', ADDRESS = 'SIKKIM' WHERE ROLL_NO = 1;
```

**输出：**
上面的查询将更新第一行的两列，表 `Student` 现在看起来像：

| ROLL_NO | NAME | ADDRESS | PHONE | AGE |
| :--- | :--- | :--- | :--- | :--- |
| 1 | PRATIK | SIKKIM | XXXXXXXXXX | 18 |
| 2 | RAMESH | GURGAON | XXXXXXXXXX | 18 |
| 3 | PRATIK | ROHTAK | XXXXXXXXXX | 20 |
| 4 | SURESH | DELHI | XXXXXXXXXX | 18 |
| 5 | PRATIK | ROHTAK | XXXXXXXXXX | 20 |
| 6 | RAMESH | GURGAON | XXXXXXXXXX | 18 |

**注意：** 为了更新多列，我们使用了逗号（`,`）来分隔两列的名称和值。

### 省略 WHERE 子句

如果我们在更新查询中省略 `WHERE` 子句，那么所有行都将被更新。

```sql
UPDATE Student SET NAME = 'PRATIK';
```

**输出：**
表格 `Student` 现在看起来像：

| ROLL_NO | NAME | ADDRESS | PHONE | AGE |
| :--- | :--- | :--- | :--- | :--- |
| 1 | PRATIK | DELHI | XXXXXXXXXX | 18 |
| 2 | PRATIK | GURGAON | XXXXXXXXXX | 18 |
| 3 | PRATIK | ROHTAK | XXXXXXXXXX | 20 |
| 4 | PRATIK | DELHI | XXXXXXXXXX | 18 |
| 5 | PRATIK | ROHTAK | XXXXXXXXXX | 20 |
| 6 | PRATIK | GURGAON | XXXXXXXXXX | 18 |

本文由 [**Harsh Agarwal**](https://www.facebook.com/harsh.agarwal.16752) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。