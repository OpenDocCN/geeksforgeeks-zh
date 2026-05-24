# MS SQL Server 中的表操作

> 原文:[https://www . geesforgeks . org/table-operations-in-ms-SQL-server/](https://www.geeksforgeeks.org/table-operations-in-ms-sql-server/)

在[关系数据库](https://www.geeksforgeeks.org/relational-model-in-dbms/)中，数据以表格的形式存储，每个表格被称为一个关系。一个表最多可以存储 1000 行。桌子是首选，因为:

*   The tables are arranged in order.
*   We can isolate the data in rows and columns according to our own preferences.
*   Data retrieval and operation become easier.
*   Can identify whether there is duplicate data.
*   You can also add new columns without interrupting the previous data in the table.

表格由行和列组成。行称为记录，列称为字段。在 MS SQL Server 中，表是在数据库和模式名称中指定的。

**命名表的语法–**

```sql
create table[db_name] [schema_name] table_name col1 datatype,......); 
```

**示例–**

```sql
create table student 
(
name varchar2(30),
rollnumber int primary key, 
course varchar2(10)
);
```

将在数据库中创建一个名为 student 的表。可以插入如下几个值。

```sql
insert into student values('Aisha', 111, 'CSE');
insert into student values('Naina', 112, 'ECE');
```

**输出–**

<center>T20】111T22【CSET26】奈娜T30【ECE

| **Name** | **辊号** | **课程** |
| Alsa |
| One hundred and twelve |

T35】</center>

现在使用 insert 关键字插入这些值。还可以对该表执行其他操作:

**更改表格添加列:**

学生表有这么多属性。如果用户想要添加一个新列，可以按如下方式进行。

```sql
alter table table_name add column_name datatype column_constraint;
```

假设用户想在学生表中添加学生的年龄，可以按如下方式进行。

```sql
alter table student add age int; 
```

将创建年龄列。用户可以在表格中插入年龄，如下所示:

```sql
insert into student values('Aisha', 111, 'CSE', 18);
insert into student values('Naina', 112, 'ECE', 19);
```

**输出–**

**【行程】**

| **[name]** | **[volume number]** |

**更改表格拖放栏:**

在数据库的生命周期中，有些列保持未使用或很少使用。为了从表中删除它们，必须按如下方式进行。

```sql
alter table table_name drop column column_name;
```

在学生表中，年龄是一个未使用的属性。要删除该列，必须给出如下查询:

```sql
alter table student drop column age;
```

**输出–**

<center>T20】111T22【CSET26】奈娜T30【ECE

| **Name** | **辊号** | **课程** |
| Alsa |
| One hundred and twelve |

T35】</center>

它从数据库记录中删除数据。这意味着数据被永久删除，无法再次检索。