# 使用 `RANK()` 添加数据库中行的排名位置的 SQL 查询

> 原文: [https://www.geeksforgeeks.org/sql-query-to-add-ranking-positions-of-rows-in-a-database-with-rank/](https://www.geeksforgeeks.org/sql-query-to-add-ranking-positions-of-rows-in-a-database-with-rank/)

在本文中，我们将讨论 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 函数 `RANK` 的概述，然后我们的主要焦点将是在 SQL 中使用 `RANK()` 添加数据库中行的排名位置。我们一个一个来讨论。

## 概述
一般来说，执行 `max`/`min` 命令时，会显示一行作为输出。`RANK()` 是为了根据表中的某个属性对行进行排序而引入的一个 SQL 函数。基于现有值的记录，`RANK` 函数将帮助相应地对列进行排序。

## 语法
```sql
RANK() OVER(ORDER BY Any Column)
```

## 实现 `RANK` 函数的步骤
这里，我们将讨论在 SQL 中实现 `RANK` 函数的步骤。

### 步骤-1: 参考表
考虑一个基于班级中学生的分数创建的表，该表包含下面显示的数据。

| 身份证明 | 名字 | 数学 | 物理学 | 化学 |
| --- | --- | --- | --- | --- |
| 501 | Surya | 99 | 97 | 85 |
| 502 | Charan | 99 | 93 | 88 |
| 503 | Sravan | 91 | 98 | 94 |
| 504 | Ram | 92 | 99 | 82 |
| 505 | Aryan | 94 | 99 | 88 |
| 506 | Sathwik | 91 | 88 | 91 |
| 507 | Madhav | 90 | 97 | 89 |

### 第 2 步: 创建表
现在，用于创建该表的 SQL 语句如下。

```sql
CREATE TABLE MarkList
(
id int,
name varchar(20),
mathematics int, 
physics int,
chemistry int
);
```

### 步骤-3: 插入数据
这里，我们将按如下方式将行插入表中。

```sql
insert into MarkList values( 501,'Surya',99,97,85);
insert into MarkList values(502,'Charan',99,93,88);
insert into MarkList values(503,'Sravan',91,98,94);
insert into MarkList values(504,'Ram',92,99,82);
insert into MarkList values(505,'Aryan',94,99,88);
insert into MarkList values(506,'Sathwik',91,88,91);
insert into MarkList values(507,'Madhav',90,97,89);
```

### 步骤-4: 验证和排名数据
现在，如果我们想要基于数学成绩的排名，那么查询如下。

```sql
SELECT id, name, mathematics,
RANK() OVER(ORDER BY Mathematics DESC) 
as 
'Rank' from MarkList;
```

## 输出
输出如下。

| id | name | mathematics | Rank |
| --- | --- | --- | --- |
| 501 | Surya | 99 | 1 |
| 502 | Charan | 99 | 1 |
| 505 | Aryan | 94 | 3 |
| 504 | Ram | 92 | 4 |
| 503 | Sravan | 91 | 5 |
| 506 | Sathwik | 91 | 5 |
| 507 | Madhav | 90 | 7 |

## 说明
*   当执行 SQL 命令时，该函数检查顺序，并将等级分配给相应的行。
*   然后根据给定的代码显示带有等级的表格。

## 其他方法
还有很多其他方法可以代替 `RANK()`。这里列出了其中的一些。
*   `ROW_NUMBER()` 只是在排名的位置加上行号。
*   `DENSE_RANK()` 只是给出下一个数字作为下一个等级。这不取决于其他级别的频率。