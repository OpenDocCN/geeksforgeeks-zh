# 使用联合子句的 SQL 完全外部连接

> 原文:[https://www . geesforgeks . org/SQL-full-outer-join-use-union-子句/](https://www.geeksforgeeks.org/sql-full-outer-join-using-union-clause/)

在本文中，我们将讨论 SQL 的概述，我们的主要焦点将是如何在 SQL 中使用 Union 子句执行完全外部连接。我们一个一个来讨论。

**概述:**
要管理关系数据库， [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 是一种结构化查询语言，用于执行创建、维护数据库表、从数据库中检索信息等操作。这里我们将看到如何使用联合子句创建 SQL 完全外部连接。如果数据库不允许完全连接(MySQL 不允许)，您可以使用 UNION 子句组合左连接和右连接。

**使用 Union 子句实现 SQL 完全外部连接的步骤:**
这里，我们将首先创建一个名为“极客”的数据库，然后在该数据库中创建两个表“部门”和“员工”。

**步骤-1:创建数据库:**
使用如下 SQL 查询创建数据库。

```sql
CREATE geeks;
```

**第 2 步:使用数据库:**
要使用这个数据库使用如下 SQL 查询如下。

```sql
USE geeks;
```

**步骤-3:创建表:**
使用 SQL 查询在‘极客’数据库中创建表“部门”，如下所示。

```sql
CREATE TABLE department
(
   ID int,
   SALARY int,
   NAME Varchar(20),
   DEPT_ID Varchar(255)
);
```

**第 4 步:插入数据:**
使用如下 SQL 查询向表中添加值。

```sql
INSERT INTO department VALUES (1, 34000, 'ANURAG', 'UI DEVELOPERS');
INSERT INTO department VALUES (2, 33000, 'HARSH', 'BACKEND DEVELOPERS');
INSERT INTO department VALUES (3, 36000, 'SUMIT', 'BACKEND DEVELOPERS');
INSERT INTO department VALUES (4, 36000, 'RUHI', 'UI DEVELOPERS');
INSERT INTO department VALUES (5, 37000, 'KAE', 'UI DEVELOPERS');
```

**第 5 步:验证插入的数据:**
如下选择表格内的数据。

```sql
SELECT * FROM department;
```

**输出:**

<figure class="table">2T30】33000

| 身份证明 | 薪水 | 名字 | 部门标识 |
| --- | --- | --- | --- |
| one | Thirty-four thousand | 阿努格 | 用户界面开发人员 |
|  |
| five | Thirty-seven thousand | KAE | 用户界面开发者 |

</figure>

**第 6 步:创建表:**
在‘geek sdb’数据库中创建表“employee”，如下所示。

```sql
Create Table employee(
 ID int,
 Email Varchar(255),
 City Varchar(20) 
);
```

**第 7 步:插入值:**
将值添加到表“员工”中，如下所示。

```sql
INSERT INTO employee VALUES (1, 'ANURAG@xyz.com', 'Noida');
INSERT INTO employee VALUES (2, 'HARSH@xyz.com', 'Jaipur');
INSERT INTO employee VALUES (3, 'SUMIT@xyz.com', 'Noida');
INSERT INTO employee VALUES (4, 'RUHI@xyz.com', 'Jaipur');
INSERT INTO employee VALUES (5, 'KAE@xyz.com', 'Noida');
```

**第 8 步:验证插入的数据:**
选择表格内的数据如下。

```sql
SELECT * FROM employee;
```

**输出:**

<figure class="table">

| 【id】 | [e-mail] |
| --- | --- |

</figure>

**第 9 步:使用 Union 子句执行完全外部联接:**
使用 Union 子句创建 SQL 完全外部联接。如果数据库不允许完全连接(MySQL 不允许)，您可以使用 UNION 子句组合左连接和右连接。
**语法–**

```sql
SELECT  *
  FROM table1
  LEFT JOIN table2
  ON table1.columname = table2.columname
UNION 
  SELECT *
  FROM table1
  RIGHT JOIN table2
   ON table1.columname = table2.columname
```

**示例–**

```sql
SELECT  *
 FROM department
 LEFT JOIN employee
On department.ID = employee.ID
UNION
 SELECT *
 FROM department
 RIGHT JOIN employee
 On department.ID = employee.ID
```

**输出:**

<figure class="table">

| 【id】 | [salary] | 【 name 】 | 【部门 _ id】 | three | 【36000】 | 【苏米特】 |  | sumit @ XYZ。【com】T1】黑色 T3】

 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |

</figure>