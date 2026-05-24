# MySQL PARTITION BY 子句

> 原文：[https://www.geeksforgeeks.org/mysql-partition-by-clause/](https://www.geeksforgeeks.org/mysql-partition-by-clause/)

一个 `PARTITION BY` 子句用于将表的行划分成组。当我们必须使用一个组的其他行对该组的单个行执行计算时，这很有用。

*   它总是用在 `OVER()` 子句中。
*   由 `PARTITION BY` 子句形成的分区也称为**窗口**。
*   此子句仅适用于窗口函数，例如 `RANK()`、`LEAD()`、`LAG()` 等。
*   如果 `OVER()` 子句中省略了此子句，则整个表被视为单个分区。

## 语法

`PARTITION BY` 子句的语法是：

```sql
window_function (expression)
    OVER (PARTITION BY expr [ORDER_CLAUSE] [FRAME_CLAUSE])
```

这里，`ORDER_CLAUSE` 和 `FRAME_CLAUSE` 是可选的。

`expr` 可以是列名，也可以是 MySQL 中的内置函数。但是，标准的 SQL 只允许表达式中的列名。

## 示例

考虑一张表“黑客”：

| h_id | hgame | challenge_id | score |
| :--- | :--- | :--- | :--- |
| three | 舒卜 | 111 | 20 |
| Two | 哦，天啊 | 111 | 80 |
| five | 克里提克 | 112 | 40 |
| five | 克里提克 | 114 | 90 |
| four | 塔斯哈尔 | 112 | 30 |
| one | 聚会 | 112 | 40 |

我们必须找到黑客在每个挑战中的排名。这意味着我们必须列出所有参与挑战的黑客以及他们在挑战中的排名。

### 查询

```sql
SELECT challenge_id, h_id, hgame, score,
    DENSE_RANK() OVER (PARTITION BY challenge_id ORDER BY score DESC)
        AS `rank`
FROM hacker;
```

### 说明

在上面的查询中，`PARTITION BY` 子句进行分区，将表划分为具有相同 `challenge_id` 的组。

`ORDER BY` 会按 `score` 降序排列每个分区的黑客。

`OVER()` 子句定义了如何对表的行进行划分和排序，该表将由窗口函数 `RANK()` 处理。

`DENSE_RANK()` 是一个窗口函数，它会在挑战的有序分区中分配等级。如果两个黑客有相同的分数，那么他们将被分配相同的等级。

### 输出

| challenge_id | h_id | hgame | score | rank |
| :--- | :--- | :--- | :--- | :--- |
| 111 | Two | 哦，天啊 | 80 | 1 |
| 111 | three | 舒卜 | 20 | 2 |
| 112 | five | 克里提克 | 40 | 1 |
| 112 | one | 聚会 | 40 | 1 |
| 112 | four | 塔斯哈尔 | 30 | 2 |
| 114 | five | 克里提克 | 90 | 1 |

因此，我们得到了所有黑客的名单以及他们在个人挑战中的排名。