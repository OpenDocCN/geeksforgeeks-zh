# 在 MS SQL Server 中使用 `SELECT INTO` 和临时表

> 原文: [https://www.geeksforgeeks.org/select-into-and-temporary-tables-in-ms-sql-server/](https://www.geeksforgeeks.org/select-into-and-temporary-tables-in-ms-sql-server/)

## 1. `SELECT INTO`

假设一个表有一些特定的行，必须转移到同一数据库的另一个表。可以使用 `SELECT INTO` 语句，如下所示：

```sql
SELECT list INTO destination FROM source [WHERE condition]
```

**示例：**
有 `student` 和 `marks` 两个表。学生的分数必须从 `marks` 转移到 `student` 表。这必须按照以下步骤进行：

```sql
SELECT * FROM student;
```

| 名字 | rollno | 课程 |
| :--- | :--- | :--- |
| Maya | 111 | 中学生毕业考试 |
| Naina | 112 | 欧洲经济委员会 |
| Police | 113 | 东方马脑脊髓炎 |
| Clara | 114 | 技工 |

```sql
SELECT * FROM marks;
```

| 名字 | rollno | mks |
| :--- | :--- | :--- |
| Maya | 111 | 85 |
| Naina | 112 | 75 |
| Police | 113 | 65 |
| Clara | 114 | 55 |

```sql
SELECT mks INTO student FROM marks;
```

| 名字 | rollno | 课程 | mks |
| :--- | :--- | :--- | :--- |
| Maya | 111 | 中学生毕业考试 | 85 |
| Naina | 112 | 欧洲经济委员会 | 75 |
| Police | 113 | 东方马脑脊髓炎 | 65 |
| Clara | 114 | 技工 | 55 |

分数将被添加到 `student` 表格中。`WHERE` 子句可用于条件，它是可选的。

## 2. 临时表

用户有时希望根据给定的表值创建一个单独的表。这必须使用临时表的概念来完成。可以通过两种方式创建临时表：使用 `CREATE TABLE` 语法或 `SELECT INTO` 语法。

### 使用 `SELECT INTO`

必须使用 `SELECT INTO` 语句从 `student` 表创建一个新表，如下所示：

```sql
SELECT * FROM student;
```

| 名字 | rollno | 课程 |
| :--- | :--- | :--- |
| Maya | 111 | 中学生毕业考试 |
| Naina | 112 | 欧洲经济委员会 |
| Police | 113 | 东方马脑脊髓炎 |
| Clara | 114 | 技工 |

```sql
SELECT name, rollno INTO #details FROM student;
```

| 名字 | rollno |
| :--- | :--- |
| Maya | 111 |
| Naina | 112 |
| Police | 113 |
| Clara | 114 |

### 使用 `CREATE TABLE`

可以使用 `CREATE TABLE` 语句创建新表：

```sql
CREATE TABLE #details( name varchar2(30), rollno int);
```

将创建一个新表。这些值可以从其他表中复制，如下所示：

```sql
INSERT INTO #details SELECT name, rollno FROM student;
```

| 名字 | rollno |
| :--- | :--- |
| Maya | 111 |
| Naina | 112 |
| Police | 113 |
| Clara | 114 |