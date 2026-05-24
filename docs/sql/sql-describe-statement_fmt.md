# SQL DESCRIBE 语句

> 原文: [https://www.geeksforgeeks.org/sql-describe-statement/](https://www.geeksforgeeks.org/sql-describe-statement/)

**先决条件:** [Sql Create 子句](https://www.geeksforgeeks.org/sql-create/)

顾名思义，`DESCRIBE` 用来描述某物。因为在数据库中我们有表，所以我们使用 `DESCRIBE` 或 `DESC`（两者相同）命令来描述表的结构。

## 语法

```sql
DESCRIBE one;
  OR
DESC one;
```

**注意:** 我们可以使用 `DESCRIBE` 或者 `DESC`（两者都是不区分大小写）。

假设我们的表名为 `one`，有 `3` 列，名为 `FIRST_NAME`、`LAST_NAME` 和 `SALARY`，所有这些都可以包含空值。

## 输出

```sql
Name          Null       Type
FIRST_NAME              CHAR(25)
LAST_NAME               CHAR(25)
SALARY                  NUMBER(6)
```

- 这里，在上面使用 `DESC` 或者 `DESCRIBE` 我们可以看到一个表的结构，但是在控制台选项卡上不是，表的结构显示在数据库系统软件的描述选项卡中。
- 因此 `DESC` 或 `DESCRIBE` 命令显示了表的结构，包括列的名称、列的数据类型和可空性，这意味着该列可以包含或不包含空值。
- 表的所有这些特征都在创建表时描述。

## 示例

### 创建表格或定义表格的结构

```sql
create table one
(
id int not null, 
name char(25)
)
```

在这里，我们创建了一个名为 `one` 的表，其列为 `ID`、`NAME`，并且 `id` 属于非空类型，即我们不能将空值放入 `ID` 列，但是我们可以将空值放入 `NAME` 列。

### 演示 DESC 的示例

**第一步:** 定义表格的结构，即创建表格:

```sql
create table one
(
 id int not null,
 name char(25),
 city varchar2(25)
)
```

**第二步:** 显示表格结构:

```sql
DESC one
  OR
DESCRIBE one
```

```sql
Output:
Name      Null       Type
ID       Not Null    INT
NAME                CHAR(25)
CITY                VARCHAR2(25)
```

**注:** 此处上方 `ID` 列为非空类型，其余 2 列可包含空值。

**注意:** 你只需要在你的系统软件上执行 `DESC` 命令，因为这个命令不会在任何编辑器上运行。请确保仅在您自己安装的数据库上运行此命令。

**参考文献:** [Oracle.com](https://docs.oracle.com/javadb/10.8.3.0/tools/rtoolsijcomrefdescribe.html)

本文由 **Rajat Rawat 4** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。