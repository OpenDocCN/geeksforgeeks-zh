# MySQL DEFAULT()函数

> 原文: [https://www.geeksforgeeks.org/mysql-default-function/](https://www.geeksforgeeks.org/mysql-default-function/)

`DEFAULT()` 函数返回表列的默认值。

**默认值**一列的值是在用户没有指定值的情况下使用的值。

为了使用这个函数，应该给列分配一个默认值。否则，会产生错误。

## 语法

```sql
DEFAULT (column_name)
```

`column_name`: Name of column whose default value is written.

## 例

考虑两个关系`学生`和`成绩`–

表`学生`的结构

| field | type | null |
| --- | --- | --- |
| sid | int(11) | NO |
| sname | varchar(30) | NO |
| subject | varchar(30) | NO |
| marks | int(11) | YES |

表`结果`的结构

| field | type | null | default |
| --- | --- | --- | --- |
| lowest_marks | int(11) | YES | NULL |
| highest_marks | int(11) | YES | NULL |
| grade | varchar(30) | YES | FAIL |

表格中的数据-

```sql
Select * from student;
```

| sid | name | Subject | mark |
| --- | --- | --- | --- |
| 1 | T99 | Maths | 90 |
| 2 | Shanu | E.S. | 60 |
| 3 | T15 | AT17 | 85 |
| 4 | T19 | 60 | T21 |
| 5 | 85 | T23 | B |
| 6 | T25 | T27 | 40 |
| 7 | 60 | T31 | C |

```sql
Select * from result;
```

| Lowest_score | Maximum_score | grade |
| --- | --- | --- |
| eighty-five | One hundred | A |
| 70 | 84 | B |
| 60 | 69 | C |
| 0 | 59 | FAIL |

## 问题描述

我们要找到所有学生的成绩-

## 查询

```sql
Select sid, sname, subject, marks, 
    IF ( grade is NULL, DEFAULT ( grade ), grade )
AS grade  FROM  student LEFT JOIN result 
    ON marks > lowest_marks 
AND marks < = highest_marks;
```

## 输出

| sid | name | Subject | mark | grade |
| --- | --- | --- | --- | --- |
| 1 | T99 | Maths | 90 | A |
| 2 | Shanu | E.S. | 60 | C |
| 3 | T15 | AT17 | 85 | A |
| 4 | T19 | 60 | T21 | FAIL |
| 5 | 85 | T23 | B | FAIL |
| 6 | T25 | T27 | 40 | FAIL |
| 7 | 60 | T31 | C | FAIL |

## 说明

这里使用`default()`函数返回默认等级，即“FAIL”。此默认值用于学生分数与加入条件不符的地方。那些学生的成绩显示为不及格。

## 注意

带有`select`语句的默认函数将返回所有行的默认值。这意味着，我们将获得该列的默认值列表，而不是该列的单个默认值。

例如上表`结果`，查询输出为-

```sql
Select default ( grade) from result;
```

输出:

| default (grade) |
| --- |
| A |
| B |
| C |
| FAIL |