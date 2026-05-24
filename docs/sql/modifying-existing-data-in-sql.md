# 修改 SQL 中已有的数据

> 原文:[https://www . geesforgeks . org/modification-existing-data-in-SQL/](https://www.geeksforgeeks.org/modifying-existing-data-in-sql/)

在本文中，我们将介绍如何在 SQL 中修改现有数据。在很多情况下，我们需要改变和更新现有的数据。我们一个一个来讨论。

**1。** [**ALTER 命令**](https://www.geeksforgeeks.org/sql-alter-add-drop-modify/) **:**
ALTER 是关系型数据库管理系统中使用的一个 SQL 命令，是一个数据定义语言(DDL)语句。ALTER 可用于更新数据库中的表结构(如添加、删除、删除索引、列和约束，修改数据库中表的属性)。

ALTER 命令最常用于通过添加和删除索引来改进 SQL SELECT 查询。

**语法:**
**向现有表格添加一列–**

```sql
ALTER TABLE tableName 
ADD columnName columnDefinition;
```

**示例–**

```sql
ALTER TABLE Student 
ADD marks_obtained Number (3);
```

**之前:学生表**

<figure class="table">桑托什 T30】10

| (full) name | classes | contact | city |
| --- | --- | --- | --- |
| Asu | Ten | Ninety thousand | Delhi |
| Nine thousand |

</figure>

**之后:学生表**

marks _ 获得了

<figure class="table">T15T18】10T20】90000T22】德里 T24】T25T28【10】T30【90001】T31

| name | kind | contact | city |
| --- | --- | --- | --- |
| Asu | Santosh |

</figure>

**语法:**
**从现有表中删除列–**

```sql
ALTER TABLE tableName 
DROP COLUMN columnName;
```

**示例–**

```sql
ALTER TABLE Student 
DROP COLUMN city;
```

**之前:学生表**

<figure class="table">桑托什 T30】10

| (full) name | classes | contact | city |
| --- | --- | --- | --- |
| Asu | Ten | Ninety thousand | Delhi |
| Nine thousand |

</figure>

**之后:学生表**

<figure class="table">

| 名字 | 班级 | 接触 |
| --- | --- | --- |
| 阿苏 | Ten | Ninety thousand |
| 桑托什 | Ten | Ninety thousand and one |
| 潘卡伊 | Ten | Ninety thousand and two |
| 迪帕克 | Ten | Ninety thousand and three |

</figure>

**语法:**

**更改现有表中的列名–**

```sql
ALTER TABLE tableName 
RENAME COLUMN olderName TO newName;
```

**示例–**

```sql
ALTER TABLE student 
RENAME COLUMN contactTO contact_no;
```

**之前:学生表**

<figure class="table">桑托什 T30】10

| (full) name | classes | contact | city |
| --- | --- | --- | --- |
| Asu | Ten | Ninety thousand | Delhi |
| Nine thousand |

</figure>

**后:学生表**

<figure class="table">T18】阿苏 T20【10】T21T24】德里T27T30】10T32】

| (full) name | classes | Contact _ none | city |
| --- | --- | --- | --- |
| Ninety thousand |
| Santosh |

</figure>

**2。** [**更新命令**](https://www.geeksforgeeks.org/sql-update-statement/) **:**

UPDATE 是关系数据库管理系统中使用的一个 SQL 命令，是一个数据操作语言语句。它用于操作任何现有列的数据。但是不能改变表的定义。

**语法:**
**更新现有表中的数据–**

```sql
UPDATE table_name 
SET column1 = value1, 
column2 = value2, ... WHERE condition;
```

**示例–**

```sql
UPDATE student 
SET contact = 91111\. WHERE name =ashu;
```

**之前:学生表**

<figure class="table">桑托什 T30】10

| (full) name | classes | contact | city |
| --- | --- | --- | --- |
| Asu | 10 | Ninety thousand | Delhi |
| Nine thousand |

</figure>

如果没有 WHERE 子句，表中的所有记录都将被更新。

[**SQL 中 ALTER 和 UPDATE 命令的区别**](https://www.geeksforgeeks.org/difference-between-alter-and-update-command-in-sql/)**:**

<figure class="table">

| ALTER command | 更新命令 |
| --- | --- |
| It is a data definition language (DDL). | Is data manipulation language (DML). |
| It affects the structure of the table. | Data that affects the table. |
| Used to add, delete, delete indexes, columns and constraints, and modify the attributes of tables in the database. | Used to update existing data in the database. |
| Null value is given in tuple by default after initialization. | Give the specified value in the table specified in the command. |
| Examples-table name, function, table structure, etc. | Change the data entry of a specified column or row. |

</figure>