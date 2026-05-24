# SQL 中的主键约束

> 原文:[https://www . geesforgeks . org/primary-key-constraint-in-SQL/](https://www.geeksforgeeks.org/primary-key-constraint-in-sql/)

主键约束描述了包含一个或多个列的键，这些列将有助于唯一地标识表中的每个元组/记录。

**属性:**

1.  不允许重复值，即分配为主关键字的列只能有唯一值。
2.  主键列中不存在空值。因此，在具有主键的列中有强制值。
3.  每个表只存在一个主键，尽管主键可能有多列。
4.  不能用已经存在的主键插入新行。
5.  分类为:a)具有单列的简单主键 2)具有多列的复合主键。
6.  在创建表/更改表语句中定义。

可以使用主键约束在表中创建主键。它可以在两个级别创建。

1.  圆柱
2.  桌子。

**列级 SQL PRIMARY KEY:**
如果 PRIMARY KEY 只包含一列，应该在列级定义。下面的代码在人员表上创建主键“标识”。

**语法:**

```sql
Create Table Person
(
Id int NOT NULL PRIMARY KEY, 
Name varchar2(20), 
Address varchar2(50)
);

```

这里添加了非空值，以确保标识应该具有唯一的值。如果未指定主键，SQL 将自动为其设置空值。

**例-1 :**
**验证主键工作:**

```sql
Insert into Person values(1, 'Ajay', 'Mumbai');

```

**输出:**

```sql
1 row created

```

**示例-2 :**
让我们看看你是否会再次插入相同的值。

```sql
Insert into Person values(1, 'Ajay', 'Mumbai');
```

**输出:**

```sql
Error at line 1: unique constraint violated

```

由于我们正在插入重复的值，将会抛出一个错误，因为主键“标识”只能包含唯一的值。

**示例-3 :**

```sql
Insert into Person values('', 'Ajay', 'Mumbai');

```

**输出:**

```sql
Error at line 1: cannot insert Null into<"user"."Person"."ID">

```

主键不能包含空值，这样也会引发错误。

**表级的 SQL 主键:**
当主键包含多列时，必须在表级指定它。

语法:

```sql
Create Table Person
(Id int NOT NULL, 
Name varchar2(20), 
Address varchar2(50), 
PRIMARY KEY(Id, Name)
);                

```

这里，一个表中只有一个主键，但它由多个列(标识、名称)组成。然而，以下是允许的。

```sql
Insert into Person values(1, 'Ajay', 'Mumbai');
Insert into Person values(2, 'Ajay', 'Mumbai');

```

因为多个列组成主键，所以这两行被认为是不同的。SQL 允许这两个值中的任何一个可以重复，但是组合必须是唯一的。

**带 ALTER TABLE 的 SQL 主键:**
大多数情况下，主键是在创建表的过程中定义的，但有时主键可能不会在已经存在的表中创建。但是，我们可以使用 Alter 语句添加主键。

**语法:**

```sql
Alter Table Person add Primary Key(Id);

```

使用以下查询在多列中添加主键。

```sql
Alter Table Person add Primary Key(Id, Name);

```

作为主键添加的列必须包含唯一值，否则会被违反。如果一个标识包含重复值，则不能成为主键。它违反了主键的基本规则。更改表以添加标识作为可能包含重复值的主键会产生错误。

**输出:**

```sql
Error at line 1: cannot validate- primary key violated

```

此外，使用 alter 语句作为主键添加的列不应有空值。更改表以添加可能包含空值的标识作为主键会产生错误。

**输出:**

```sql
Error at line 1: column contains NULL values; cannot alter to NOT NULL

```

**删除主键约束:**
要删除表的主键约束，请使用给定的 SQL，如下所示。

```sql
ALTER table Person DROP PRIMARY KEY;

```