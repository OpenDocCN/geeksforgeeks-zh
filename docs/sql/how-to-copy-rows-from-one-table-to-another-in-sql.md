# 如何在 SQL 中将行从一个表复制到另一个表？

> 原文:[https://www . geeksforgeeks . org/如何在 sql 中将一个表中的行复制到另一个表中/](https://www.geeksforgeeks.org/how-to-copy-rows-from-one-table-to-another-in-sql/)

在本文中，我们学习了如何在 SQL 中将行从一个表复制到另一个表。为了更好地理解，我们将借助一个示例来实现这个查询。每当我们在不同的表中需要两个或多个相同的列时，这个查询非常有帮助。这一次我们确实需要在另一个表的帮助下手动将记录插入表中。我们可以直接从另一个表中复制记录。首先，我们将创建一个数据库名称作为示例，然后我们将在数据库示例中创建两个表。第一个表名是 EMPOLYEET，第二个是出勤表。

**我们将在这里使用两个语句**

*   插入语句
*   选择指令

我们将按照以下步骤实现如何在 SQL 中将行从一个表复制到另一个表:

**步骤 1:** 创建数据库

对于数据库创建，有一个我们将在 SQL 平台中使用的查询。这是查询。

**语法:**

```sql
Create database database_name; 
```

**查询:**

```sql
CREATE DATABASE Sample; // query will create a database in SQL Platform 
```

**步骤 2:** 使用数据库

为了使用数据库，我们将在 SQL 平台中使用另一个查询，如 Mysql、oracle 等。

**查询:**

```sql
use Sample;  
```

**步骤 3:** 创建表格

对于创建数据表，我们将在下面使用它

**查询:**

```sql
create table table_name(
column1 type(size),
column2 type(size),
.
columnN type(size)
); 
```

这将在现有数据库中创建一个新表。

**查询:**

```sql
CREATE TABLE EMPLOYEE
(
EMPNAME VARCHAR(25),
GENDER VARCHAR(6),
DEPT VARCHAR(20),
CONTACTNO BIGINT NOT NULL,
CITY VARCHAR(15)
); 
```

现在我们将创建另一个表名“出勤”

**查询:**

```sql
CREATE TABLE ATTENDANCE
( EMPNAME VARCHAR(25),
GENDER VARCHAR(6),
DEPT VARCHAR(20),
ATTENDATE DATE DEFAULT GETDATE()
); 
```

**步骤 4:** 将数据插入表 EMPOLYEET

**查询:**

```sql
INSERT INTO EMPLOYEET
VALUES ('VISHAL','MALE','SALES',9193458625,'GAZIABAD'),
('DIVYA','FEMALE','MANAGER',7352158944,'BARIELLY'),
('REKHA','FEMALE','IT',7830246946,'KOLKATA'),
('RAHUL','MALE','MARKETING',7906334516,'MEERUT'),
('SANJAY','MALE','SALES',9149335694,'MORADABAD'),
('RAJKUMAR','MALE','MANAGER',9675274391,'BENGALURU'),
('RAJSHREE','FEMALE','SALES',9193458625,'VODODARA'),
('HAIM','MALE','IT',7088573213,'SAMBHAL'),
('RAKESH','MALE','MARKETING',9645956441,'BOKARO'),
('MOHINI','FEMALE','SALES',9147844694,'Dehli'); 
```

**步骤 5:** 验证或查看员工表中插入的数据

在表中插入数据后，我们可以调整或确认哪些数据必须正确插入或不正确插入。借助下面的查询。

**查询:**

```sql
 SELECT * FROM EMPLOYEET; 
```

**输出:**

![](img/1059f448c2640dea397c57f3fe02a2d6.png)

**第 6 步:**将数据插入考勤表

在此表中，我们不会手动插入记录，因为相同的数据存在于另一个表 EMPLOYEET 中，因此，我们将数据从 EMPLOYEET 表复制到出勤表。用下面的查询

**查询:**

```sql
INSERT INTO ATTENDENCE (EMPNAME,GENDER,DEPT)
SELECT EMPNAME,GENDER,DEPT FROM EMPLOYEET; 
```

在表中插入数据后，我们可以调整或确认我们从 EMPLOYEET 复制的记录中插入的数据是否正确。借助下面的查询。

**查询:**

```sql
SELECT * FROM ATTENDENCE;
```

现在我们可以在下面的快照中看到正确复制的记录

**输出:**

![](img/1dbab716c297af1970a1bea94b0328a5.png)