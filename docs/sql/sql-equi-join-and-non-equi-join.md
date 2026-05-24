# SQL |等联接和非等联接

> 原文:[https://www . geesforgeks . org/SQL-eqi-join-and-non-eqi-join/](https://www.geeksforgeeks.org/sql-equi-join-and-non-equi-join/)

在[左、右、全连接](https://www.geeksforgeeks.org/sql-join-set-1-inner-left-right-and-full-joins/)和 [SQL | Join(笛卡尔连接&自连接)](https://www.geeksforgeeks.org/sql-join-cartesian-join-self-join/?ref=lbp)中解释了 SQL 连接的类型。和保持平等加入和不N-平等将在本文中讨论。我们一个一个来讨论。

[SQL JOINS](https://www.geeksforgeeks.org/sql-join-set-1-inner-left-right-and-full-joins/)**:**

*   EQUI [加入](https://www.geeksforgeeks.org/sql-join-set-1-inner-left-right-and-full-joins/)
*   否不相等连接

**示例–**

让我们考虑下面给出的两个表格。

表名-学生

在这个表格中，你有我，名字，班级和城市是字段。

```sql
Select * from Student;
```

T133T19】德里 T21T23】4T25】梅嘎 T27】2 德里T32T35

| 身份证明（identification） | name | kind | city |
| --- | --- | --- | --- |
| Hina | three |
| Delhi |
| six |

表名—记录

在这张表中，你有我，阶级和城市是领域。

```sql
Select * from Record;
```

19T23】德里T27】12T31】德里T35】

| 身份证明（identification） | kind | city |
| --- | --- | --- |
| nine | three | Delhi |
| Ten | Two |
| Two |

**1。EQUI JOIN :**

EQUI JOIN 为相关表的相等或匹配列值创建一个 JOIN。EQUI JOIN 还通过将 JOIN 与 ON 一起使用，然后提供列的名称及其相对表来创建 JOIN，以使用等号(=)检查相等性。

**语法:**

```sql
SELECT column_list  
FROM table1, table2....
WHERE table1.column_name =
table2.column_name;  

```

**示例–**

```sql
SELECT student.name, student.id, record.class, record.city
FROM student, record
WHERE student.city = record.city;
```

或者

**语法:**

```sql
SELECT column_list
FROM table1  
JOIN table2
[ON (join_condition)]

```

**示例–**

```sql
SELECT student.name, student.id, record.class, record.city
FROM student
JOIN record
ON student.city = record.city;
```

**输出:**

| 【 name 】 | 【id】 | [category] | [city] |
| --- | --- | --- | --- |
|  | [Delhi] |
| 【古丽】 |  | 【2】 | [Delhi] |

**2。非等连接:**

NON EQUI JOIN 使用等号(=)以外的比较运算符执行连接，如>、 =、< =和条件。

**语法:**

```sql
SELECT *  
FROM table_name1, table_name2  
WHERE table_name1.column [> |  < |  >= | <= ] table_name2.column;

```

**示例–**

```sql
SELECT student.name, record.id, record.city
FROM student, record
WHERE Student.id < Record.id ;
```

**输出:** 【德里】

| 【 name 】 | 【id】 | [city] |
| --- | --- | --- |
| [China] |
| --- |
| [China] | 【12】 |
| --- | --- |
| 【megha】 | 【12】 |
| --- | --- |