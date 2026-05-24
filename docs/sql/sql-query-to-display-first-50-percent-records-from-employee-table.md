# 显示员工表前 50%记录的 SQL 查询

> 原文:[https://www . geesforgeks . org/SQL-查询-显示-第一-50-百分比-记录-来自员工-表/](https://www.geeksforgeeks.org/sql-query-to-display-first-50-percent-records-from-employee-table/)

在这里，我们将看到如何在 **MS SQL server 的**数据库中显示员工表中的前 50%的记录。

为了演示的目的，我们将在名为“*极客*的数据库中创建一个*员工*表。

### **创建数据库:**

使用下面的 SQL 语句创建一个名为 geeks 的数据库:

```sql
CREATE DATABASE geeks;
```

### **使用数据库:**

```sql
USE geeks;
```

### 表格定义:

我们的*极客*数据库中有以下员工表:

```sql
CREATE TABLE Employee(
ID INT PRIMARY KEY AUTO_INCREMENT,
NAME VARCHAR(30) NOT NULL,
PHONE INT(10) NOT NULL UNIQUE,
EMAIL VARCHAR(30) NOT NULL UNIQUE,
DATE_OF_JOINING DATE);
```

您可以使用以下命令查看表格说明:

```sql
 EXEC SP_COLUMNS Employee;
```

![](img/eb20e31568ebb0eb731144b86c29f4fa.png)

### 向表中添加数据:

使用以下语句向*员工*表添加数据:

```sql
INSERT INTO Employee (NAME, PHONE, EMAIL, DATE_OF_JOINING)
VALUES
('Yogesh Vaishnav', 0000000001, 'yogesh@mail.com', '2019-10-03'),
('Vishal Vishwakarma', 0000000002, 'chicha@mail.com', '2019-11-07'),
('Ajit Yadav', 0000000003, 'ppa@mail.com', '2019-12-12'),
('Ashish Yadav', 0000000004, 'baba@mail.com', '2019-12-25'),
('Tanvi Thakur', 0000000005, 'tanvi@mail.com', '2020-01-20'),
('Sam', 0000000006, 'sam@mail.com', '2020-03-03'),
('Ron', 0000000007, 'ron@mail.com', '2020-05-16'),
('Sara', 0000000008, 'sara@mail.com', '2020-07-01'),
('Zara', 0000000009, 'zara@mail.com', '2020-08-20'),
('Yoji', 0000000010, 'yoji@mail.com', '2020-03-10');
```

要验证表格的内容，请使用以下语句:

```sql
SELECT * FROM Employee;
```

![](img/8ff5421e2c457affa6b3edc97cf5b1d1.png)

现在让我们从雇员表中检索前 50%的记录。

### **对于 MS SQL 数据库:**

在 MS SQL 中，我们可以借助 **top** 和 **percent** 子句直接检索前 50%的记录。下面给出了一个简单的语法:

> **语法:**
> 
> 从<table_name>中选择前 N % *；/*给出数据库表中前 N %的记录*/</table_name>

**示例:**

```sql
select top 50 percent * from Employee;
```

**输出:**

![](img/87b8bb6984f56925af452e60eb317185.png)