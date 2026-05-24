# MySQL GROUP_CONCAT()函数

> 原文: [https://www.geeksforgeeks.org/mysql-group_concat-function/](https://www.geeksforgeeks.org/mysql-group_concat-function/)

MySQL 中的 `GROUP_CONCAT()` 函数用于将多行数据连接到一个字段中。这是一个聚合（分组依据）函数，如果组至少包含一个非空值，则返回一个字符串值。否则，返回空值。

## 语法

```sql
SELECT col1, col2, ..., colN
GROUP_CONCAT ( [DISTINCT] col_name1 
[ORDER BY clause]  [SEPARATOR str_val] ) 
FROM table_name GROUP BY col_name2;

col1, col2, ...colN : These are the column names of table.
col_name1: Column of the table whose values are concatenated into a single field for each group.
table_name: Name of table.
col_name2: Column of the table according to which grouping is done.
```

`GROUP_CONCAT()` 函数中各种子句的使用：

*   `Distinct`: 它消除了结果中值的重复。
*   `ORDER BY`: 将组的值按照特定的顺序进行排序，然后进行连接。
*   `SEPARATOR`: 默认情况下，组的值由逗号（`,`）运算符分隔。为了更改此分隔符值，使用了 `SEPARATOR` 子句，后跟字符串文字。给出为 `SEPARATOR 'str_value'`。

## 示例

让，考虑一个“员工”表：

| EMP_id | fname | lname | dept_id | strength |
| --- | --- | --- | --- | --- |
| 1 | Mukesh | Gupta | 2 | Strong leadership, responsible and fast learner. |
| 2 | Divesh | Tyagi | 2 | Punctual and quick learner |
| 3 | Neelam | Sharma | 3 | Critical thinking and diligent |
| 4 | Keshav | Singhal | 3 | Listening and self-motivated |
| 5 | Tanya | Jain | 1 | Hard work and goal-oriented |

### 查询

1.  使用简单的 `GROUP_CONCAT()` 函数：

```sql
SELECT emp_id, fname, lname, dept_id, 
GROUP_CONCAT ( strength ) as "strengths" 
FROM employee group by emp_id;
```

**输出：**

| EMP_id | fname | lname | dept_id | strengths |
| --- | --- | --- | --- | --- |
| 1 | Mukesh | Gupta | 2 | Strong leadership, responsible and fast learner. |
| 4 | Keshav | Singhal | 3 | Listening and critical thinking |
| 5 | Tanya | Jain | 1 | Hard work, goal orientation |

2.  使用 `DISTINCT` 子句：

```sql
SELECT dept_id, 
GROUP_CONCAT ( DISTINCT strength) 
as "employees strengths"  
from employee group by dept_id;
```

**输出：**

| dept_id | Employee strengths |
| --- | --- |
| 1 | Goal-oriented, hard work |
| 2 | Leadership, punctuality, quick learning and responsibility. |
| 3 | Critical thinking, diligence, listening and self-motivation |

3.  `ORDER BY` 子句的使用：

```sql
SELECT dept_id, 
GROUP_CONCAT ( DISTINCT emp_id ORDER BY emp_id  SEPARATOR ', ') 
as "employees ids" 
from employee group by dept_id;
```

这里，`SEPARATOR ','` 将用逗号（`,`）和空白字符分隔这些值。

**输出：**

| dept_id | Employee id |
| --- | --- |
| 1 | 5 |
| 2 | 1, 2 |
| 3 | 3, 4 |

## 如何在单个字段中串联不同列的多行

到目前为止，我们已经看到了使用 `GROUP_CONCAT()` 函数对属于同一列的多行的值进行分组。但是，使用 `CONCAT()` 函数和 `GROUP_CONCAT()` 函数，我们可以将不同行的多个列值组合成单个字段。

### 示例

考虑到上表“员工”，如果我们希望在查询中找到员工实力和员工 id，那么它被写成：

```sql
SELECT dept_id, GROUP_CONCAT ( strengths SEPARATOR '  ') as "emp-id : strengths"
FROM ( SELECT dept_id, CONCAT ( emp_id, ':', GROUP_CONCAT(strength SEPARATOR ', ') )
as "strengths" FROM employee GROUP BY emp_id )as emp GROUP BY dept_id;
```

### 解释

上面的查询由两个 `SELECT` 语句组成，一个是内部语句，一个是外部语句。

内部 `SELECT` 语句：

```sql
SELECT dept_id, concat ( emp_id, ':',
GROUP_CONCAT ( strength separator ', ' ) ) as "strengths"  
FROM employee GROUP BY emp_id
```

它将根据 `emp_id` 对雇员表的行进行分组。第一列显示 `dept_id`，第二列显示 `emp_id` 及其优势列表。

内部 `SELECT` 语句的输出：

| dept_id | strengths |
| --- | --- |
| 2 | 1: Leading, responsible and fast learners |
| 2 | 2: Punctual and fast learners |
| 3 | 3: Diligent and self-motivated. |

外部 `SELECT` 语句现在将根据 `dept_id` 对这些行进行分组。

**输出：**

| dept_id | emp-id: strengths |
| --- | --- |
| 1 | 5: Diligence and goal orientation |
| 2 | 1: Leadership, responsibility and speed-learner  2: punctuality and speed-learner |
| 3 | 3: Diligent and self-motivated.  4: Listening and self-motivated |

**注：** `GROUP_CONCAT()` 函数的结果被截断为最大长度，即 `1024`，由系统变量 `group_concat_max_len` 给出。但是，`group_concat_max_len` 变量的值可以通过使用 `SET` 命令在运行时更改为：

```sql
SET [GLOBAL | SESSION] group_concat_max_len = value;

value: It is the new value set to the variable.
```