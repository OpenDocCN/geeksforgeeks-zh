# SQL 自然连接

> 原文:[https://www.geeksforgeeks.org/sql-natural-join/](https://www.geeksforgeeks.org/sql-natural-join/)

在本文中，我们将讨论 SQL 自然连接的概述，然后主要通过示例来实现查询。我们一个一个来讨论。

**概述:**
自然连接是一种 [SQL 连接](https://www.geeksforgeeks.org/sql-join-set-1-inner-left-right-and-full-joins/)操作，它在表中公共列的基础上创建连接。要执行自然连接，两个表之间必须有一个公共属性(列)。自然连接将从多个关系中检索。它分三步走。

**语法:**
我们将使用以下语法执行自然连接查询。

```sql
SELECT *
FROM TABLE1
NATURAL JOIN TABLE2;
```

**自然连接的特征:**
在这里，我们将讨论自然连接的特征。

1.  它将执行笛卡尔乘积。
2.  它找到一致的元组并删除不一致的元组。
3.  然后删除重复的属性。

**实现 SQL 自然连接的步骤:**
这里，我们将讨论实现 SQL 自然连接的步骤如下。

**步骤 1:创建数据库:**

```sql
create database geeks;
```

**第 2 步:使用数据库:**
如下使用该数据库。

```sql
use geeks;
```

**第三步:参考表格进入数据库:**
这是我们极客数据库中的表格如下。

**表-1:** **部门–**

```sql
Create Table department
(
   DEPT_NAME Varchar(20),
   MANAGER_NAME Varchar(255)
);
```

**表-2:员工–**

```sql
Create Table employee
(
   EMP_ID int,
   EMP_NAME Varchar(20),
   DEPT_NAME Varchar(255)
);
```

**第 4 步:插入值:**
将值添加到表格中，如下所示。

```sql
INSERT INTO DEPARTMENT(DEPT_NAME,MANAGER_NAME) VALUES ( "IT", "ROHAN");
INSERT INTO DEPARTMENT(DEPT_NAME,MANAGER_NAME) VALUES ( "SALES", "RAHUL");
INSERT INTO DEPARTMENT(DEPT_NAME,MANAGER_NAME) VALUES ( "HR", "TANMAY");
INSERT INTO DEPARTMENT(DEPT_NAME,MANAGER_NAME) VALUES ( "FINANCE", "ASHISH");
INSERT INTO DEPARTMENT(DEPT_NAME,MANAGER_NAME) VALUES ("MARKETING", "SAMAY");

INSERT INTO EMPLOYEE(EMP_ID, EMP_NAME, DEPT_NAME) VALUES (1, "SUMIT", "HR");
INSERT INTO EMPLOYEE(EMP_ID, EMP_NAME, DEPT_NAME) VALUES (2, "JOEL", "IT");
INSERT INTO EMPLOYEE(EMP_ID, EMP_NAME, DEPT_NAME) VALUES (3, "BISWA", "MARKETING");
INSERT INTO EMPLOYEE(EMP_ID, EMP_NAME, DEPT_NAME) VALUES (4, "VAIBHAV", "IT");
INSERT INTO EMPLOYEE(EMP_ID, EMP_NAME, DEPT_NAME) VALUES (5, "SAGAR", "SALES");
```

**第五步:验证插入的数据:**
这是我们在表格里面的数据，如下。

```sql
SELECT * FROM EMPLOYEE;
```

**输出:**

<figure class="table">

| 【EMP _ id】 | 【电磁脉冲名称】 | 【部门名称】 |
| --- | --- | --- |

</figure>

```sql
SELECT * FROM DEPARTMENT;
```

**输出:**

<figure class="table">

| 【部门名称】 | 【经理 _ 姓名】 |
| --- | --- |

</figure>

**第 6 步:查询实现 SQL 自然连接:**

```sql
SELECT *
FROM EMPLOYEE
NATURAL JOIN DEPARTMENT;
```

**输出:**

<figure class="table">

| 【EMP _ id】 | 【电磁脉冲名称】 | 【部门名称】 | 【经理 _ 姓名】 |
| --- | --- | --- | --- |

</figure>