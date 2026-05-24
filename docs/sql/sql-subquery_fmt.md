# SQL 子查询

> 原文: [https://www.geeksforgeeks.org/sql-subquery/](https://www.geeksforgeeks.org/sql-subquery/)

在 SQL 中，子查询可以简单地定义为另一个查询中的一个查询。换句话说，我们可以说子查询是嵌入在另一个 SQL 查询的 `WHERE` 子句中的查询。

## 子查询的重要规则

*   您可以将子查询放在多个 SQL 子句中：`WHERE` 子句、`HAVING` 子句、`FROM` 子句。
*   子查询可以与 `SELECT`、`UPDATE`、`INSERT`、`DELETE` 语句以及表达式运算符一起使用。它可以是相等运算符或比较运算符，如 `=`、`>`、`>=`、`<=` 和 `Like` 运算符。
*   子查询是另一个查询中的查询。外部查询称为`主查询`，内部查询称为`子查询`。
*   子查询通常首先执行，其输出用于完成主查询或外部查询的查询条件。
*   子查询必须用括号括起来。
*   子查询位于比较运算符的右侧。
*   `ORDER BY` 命令**不能在子查询中使用**。`GROUP BY` 命令可用于执行与 `ORDER BY` 命令相同的功能。
*   对单行子查询使用单行运算符。对多行子查询使用多行运算符。

## 语法

子查询没有任何通用语法。但是，子查询在 `SELECT` 语句中使用最频繁，如下所示：

```sql
SELECT column_name
FROM table_name
WHERE column_name *expression operator* 
    ( SELECT COLUMN_NAME  from TABLE_NAME   WHERE ... );
```

## 样表

### 数据库 (DATABASE)

| NAME | ROLL_NO | LOCATION | PHONE_NUMBER |
| :--- | :--- | :--- | :--- |
| Ram | 101 | Chennai | 9988775566 |
| Raju | 102 | Coimbatore | 8877665544 |
| Sasi | 103 | Madurai | 7766553344 |
| Ravi | 104 | Salem | 8989898989 |
| Sumathi | 105 | Kanchipuram | 8989898989 |

### 学生 (STUDENT)

| NAME | ROLL_NO | SECTION |
| :--- | :--- | :--- |
| Ravi | 104 | A |
| Sumathi | 105 | B |
| Raju | 102 | A |

## 样本查询

### 1. 查询示例

显示 `DATABASE` 表中 `SECTION` 为 A 的学生的 `NAME`、`LOCATION`、`PHONE_NUMBER`。

```sql
SELECT NAME, LOCATION, PHONE_NUMBER 
FROM DATABASE 
WHERE ROLL_NO IN (
    SELECT ROLL_NO 
    FROM STUDENT 
    WHERE SECTION='A'
);
```

**解释：** 第一个子查询执行 `SELECT ROLL_NO from STUDENT where SECTION='A'`，从 `SECTION` 为 'A' 的 `STUDENT` 表中返回 `ROLL_NO`。然后外部查询执行，并从 `DATABASE` 表中返回其 `ROLL_NO` 在内部子查询结果中的学生的姓名、位置、电话号码。

**输出：**

| NAME | ROLL_NO | LOCATION | PHONE_NUMBER |
| :--- | :--- | :--- | :--- |
| Ravi | 104 | Salem | 8989898989 |
| Raju | 102 | Coimbatore | 8877665544 |

### 2. 插入查询示例

**表 1: Student1**

| NAME | ROLL_NO | LOCATION | PHONE_NUMBER |
| :--- | :--- | :--- | :--- |
| Ram | 101 | Chennai | 9988773344 |
| Raju | 102 | Coimbatore | 9909090909 |
| Ravi | 103 | Salem | 8989898989 |

**表 2: Student2**

| NAME | ROLL_NO | LOCATION | PHONE_NUMBER |
| :--- | :--- | :--- | :--- |
| Raju | 111 | Chennai | 8787878787 |
| Jyothi | 112 | Mumbai | 6565656565 |
| Sri | 113 | Coimbatore | 7878787878 |

要将 `Student2` 插入 `Student1` 表：

```sql
INSERT INTO Student1 
SELECT * FROM Student2;
```

**输出：**

| NAME | ROLL_NO | LOCATION | PHONE_NUMBER |
| :--- | :--- | :--- | :--- |
| Ram | 101 | Chennai | 9988773344 |
| Raju | 102 | Coimbatore | 9909090909 |
| Ravi | 103 | Salem | 8989898989 |
| Raju | 111 | Chennai | 8787878787 |
| Jyothi | 112 | Mumbai | 6565656565 |
| Sri | 113 | Coimbatore | 7878787878 |

### 3. 删除查询示例

删除 `Student2` 表中的学生，这些学生的序号与 `Student1` 表中的序号相同，并且位置与钦奈 (Chennai) 相同。

```sql
DELETE FROM Student2 
WHERE ROLL_NO IN ( 
    SELECT ROLL_NO 
    FROM Student1 
    WHERE LOCATION = 'chennai'
);
```

**输出：**

```sql
1 row delete successfully.
```

**显示 Student2 表：**

| NAME | ROLL_NO | LOCATION | PHONE_NUMBER |
| :--- | :--- | :--- | :--- |
| Jyothi | 112 | Mumbai | 6565656565 |
| Sri | 113 | Coimbatore | 7878787878 |

### 4. 更新查询示例

更新 `Student2` 表中的学生，其位置与 `Student1` 表中的 Raju、Ravi 相同。

```sql
UPDATE Student2 
SET NAME='geeks' 
WHERE LOCATION IN ( 
    SELECT LOCATION 
    FROM Student1 
    WHERE NAME IN ('Raju','Ravi')
);
```

**输出：**

```sql
1 row updated successfully.
```

**显示 Student2 表：**

| NAME | ROLL_NO | LOCATION | PHONE_NUMBER |
| :--- | :--- | :--- | :--- |
| Sai | 112 | Mumbai | 6565656565 |
| geeks | 113 | Coimbatore | 7878787878 |

---

本文由 **Rahul Ravi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。