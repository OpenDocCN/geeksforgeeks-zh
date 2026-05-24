# 显示两个表或查询之间不同的行

> 原文:[https://www . geeksforgeeks . org/show-两个表或查询之间的不同行/](https://www.geeksforgeeks.org/show-the-rows-that-are-different-between-two-tables-or-queries/)

[**结构化查询语言(SQL)**](https://www.geeksforgeeks.org/structured-query-language/) 是一种通用的数据库语言，用于从关系数据库(如 MySQL、Oracle 等)中构建、管理和检索数据。
这里我们将看到如何获取两个表或查询之间不同的行。

在这里，我们将首先创建一个名为“geeksdb”的数据库，然后在该数据库中创建两个表“Geektab1”和“GeekTab2”。之后，我们将对这些表执行查询。

**创建数据库:**

```sql
create geeksdb;
```

**使用该数据库:**

```sql
use geeksdb;
```

**在数据库中创建表 geek tab 1:**

```sql
Create Table Geektab1 (
   ID int,
 NAME varchar (25) );
```

**在表格中添加数值:**

```sql
INSERT INTO Geektab1 VALUES (1, 'Neha');
INSERT INTO Geektab1 VALUES (2, 'Ankit');
INSERT INTO Geektab1 VALUES (3, 'Khushi');
INSERT INTO Geektab1 VALUES (4, 'Mahesh');
```

**这是我们表里面的数据:**

```sql
SELECT * FROM DEPARTMENT;
```

<figure class="table">

| 身份证明 | 名字 |
| --- | --- |
| one | 停止 |
| Two | 鸭子！鸭子 |
| three | 库希 |
| four | 马什 |

</figure>

**在数据库中创建表 geek tab 2:**

```sql
Create Table Geektab2 (
ID int,
NAME varchar (25) );
```

**在表格中添加数值:**

```sql
INSERT INTO Geektab1 VALUES (1, 'Neha');
INSERT INTO Geektab1 VALUES (2, 'Ankit');
INSERT INTO Geektab1 VALUES (3, 'Khushi');
```

**这是我们表里面的数据:**

```sql
SELECT * FROM DEPARTMENT;
```

<figure class="table">

| 身份证明 | 名字 |
| --- | --- |
| one | 停止 |
| Two | 鸭子！鸭子 |
| three | 库希 |
| five | 科马尔 |

</figure>

我们可以在 SQL 中使用以下关键字来获取两个表之间不同的行:

*   **INTERSECT–**将向我们显示这两个表共享了哪些行。
*   **EXCEPT–**将向我们显示第一个表中不在第二个表中的所有行。

我们将看到这些表是否相似，或者使用这两个查询是否有任何变化。

**语法(INTERSECT) :**

```sql
SELECT * FROM table1
INTERSECT
SELECT * FROM table2 ;
```

**示例:**

```sql
SELECT * FROM Geektab1
EXCEPT
SELECT * FROM Geektab2 ;
```

**输出:**

<figure class="table">T19T23】AnkitT27】3T33

| 身份证明 | 名字 |
| --- | --- |
| one | 停止 |
| Two |
| 库希 |

</figure>

**语法(除外):**

```sql
SELECT * FROM table1
EXCEPT
SELECT * FROM table2 ;
```

**示例:**

```sql
SELECT * FROM Geektab1
EXCEPT
SELECT * FROM Geektab2 ;
```

**输出:**

<figure class="table">

| 身份证明 | 名字 |
| --- | --- |
| four | 马什 |

</figure>

如果第一个查询(INTERSECT)中的行数相同，则这些表是相似的。

同样，如果第二个查询(EXCEPT)的结果为空，则它们等于类似查询的结果。