# 将 FLOAT 转换为 NVARCHAR 的 SQL 查询

> 原文:[https://www . geesforgeks . org/SQL-query-convert-float-nvarchar/](https://www.geeksforgeeks.org/sql-query-to-convert-float-to-nvarchar/)

在这里，我们将看到如何使用 CAST()、convert()和 FORMAT()函数将 MS SQL Server 数据库表中的 FLOAT 数据转换为 NVARCHAR 数据。

我们将在一个名为“极客”的数据库中创建一个*人*表。

### **创建数据库:**

```sql
CREATE DATABASE geeks;
```

### **使用数据库:**

```sql
USE geeks;
```

### **表定义:**

我们的*极客*数据库中有以下*员工*表:

```sql
CREATE TABLE person(
id INT IDENTITY(1,1) PRIMARY KEY,
name VARCHAR(30) NOT NULL,
weight REAL NOT NULL);
```

您可以使用下面的语句来查询创建的表的描述:

```sql
EXEC SP_COLUMNS person;
```

![](img/767e770ae9c811679e538e719a52a24f.png)

### **向表中添加数据:**

使用以下语句将数据添加到*人*表中:

```sql
INSERT INTO person
VALUES
('Yogesh Vaishnav', 62.5),
('Vishal Vishwakarma', 70),
('Ashish Yadav', 69),
('Ajit Yadav', 71.9);
```

要验证表格的内容，请使用以下语句:

```sql
SELECT * FROM person;
```

![](img/2f07d7a6d67a83697f4f0001d4117ae3.png)

现在让我们使用三种不同的方法将 FLOAT 值转换为 nvarchar。

### **使用 CONVERT()功能:**

```sql
Syntax: SELECT CONVERT(<DATA_TYPE>, <VALUE>);
--DATA_TYPE is the type we want to convert to.
--VALUE is the value we want to convert into DATA_TYPE.
```

**示例:**

```sql
SELECT 'Weight of Yogesh Vaishnav is ' + CONVERT(NVARCHAR(20), weight) 
AS person_weight
FROM person
WHERE name = 'Yogesh Vaishnav';
```

**输出:**

![](img/68cd31f3820c84dd943e7fee8ecb7156.png)

### **使用 CAST()功能:**

```sql
Syntax: SELECT CAST(<VALUE> AS <DATA_TYPE>);
--DATA_TYPE is the type we want to convert to.
--VALUE is the value we want to convert into DATA_TYPE.
```

**示例:**

```sql
SELECT 'Weight of Yogesh Vaishnav is ' + CAST(weight as NVARCHAR(20)) 
AS person_weight
FROM person
WHERE name = 'Yogesh Vaishnav';
```

**输出:**

![](img/6e4e7386c3ef6a9ad0435af64b272a93.png)

### **使用 FORMAT()函数:**

虽然 format()函数对于格式化日期时间和不将一种类型转换为另一种类型很有用，但仍可用于将(或这里的 FORMAT)浮点值转换为 STR 值。

```sql
Syntax: SELECT FORMAT(<VALUE> , 'actual_format';
--actual_format is the format we want to achieve in a string form.
--VALUE is the value we want to format according to the actual_format.
```

**示例:**

```sql
SELECT 'Weight of Ashish Yadav is ' + FORMAT(weight, '') --'' denotes no formating
--i.e simply convert it to a string of characters.
AS person_weight
FROM person
WHERE name = 'Ashish Yadav';
```

**输出:**

![](img/0ca1733a93e44dd23e4c61164d86cbae.png)