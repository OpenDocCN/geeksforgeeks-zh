# MySQL | DEFAULT()函数

> 原文:[https://www.geeksforgeeks.org/mysql-default-function/](https://www.geeksforgeeks.org/mysql-default-function/)

**DEFAULT()** 函数返回表列的默认值。

**默认值**一列的值是在用户没有指定值的情况下使用的值。

为了使用这个函数，应该给列分配一个默认值。否则，会产生错误。

**语法:**

```sql
DEFAULT ( column_name)

column_name: Name of column whose default value is written.

```

**例:**考虑两个关系**学生**和**成绩**–

“学生”表的结构

| farmland | type | 空 |
| --- | --- | --- |
| 业主【t】 |

表“结果”的结构

<center>

| field | type | 空 | default |
| --- | --- | --- | --- |
| Lowest _ mark | int(11) | 是 | 空 |
| lohigh _ marks | int(11) | 是 | 空 |

</center>

表格中的数据-

```sql
Select * from student;

```

<center>

| 【样本号】 | name | [Subject] | mark |
| --- | --- | --- | --- |
| 1】 | 【T99】 |
|  | 【沙努】 | 【e . s。 |  |

</center>

<center>T15】AT17T19】60T21】85T23】BT25T27】4060T31】C

| Lowest _ score | Maximum _ score | grade |
| --- | --- | --- |
| eighty-five | One hundred |

</center>

**问题描述:**我们要找到所有学生的成绩-

**查询:**

```sql
Select sid, sname, subject, marks, 
    IF ( grade is NULL, DEFAULT ( grade ), grade )
AS grade  FROM  student LEFT JOIN result 
    ON marks > lowest_marks 
AND marks < = highest_marks;

```

**输出:**

【t13 级】 0

| 【样本号】 | name | [Subject] | [Failure] |
| --- | --- | --- | --- |
|  |  | [Manavit] |  | 【60】 |  |
| --- | --- | --- | --- | --- | --- |

**说明:**这里使用 default()函数返回默认等级，即“FAIL”。此默认值用于学生分数与加入条件不符的地方。那些学生的成绩显示为不及格。

**注意:**带有 select 语句的默认函数将返回所有行的默认值。这意味着，我们将获得该列的默认值列表，而不是该列的单个默认值。

例如上表**结果**，查询输出为-

```sql
Select default ( grade) from result;

```

**输出:**

<center>

| 默认（等级) |
| --- |
|  |
|  |
| FAIL |

</center>