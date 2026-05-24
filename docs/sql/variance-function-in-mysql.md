# MySQL 中的方差()函数

> 原文:[https://www.geeksforgeeks.org/variance-function-in-mysql/](https://www.geeksforgeeks.org/variance-function-in-mysql/)

有时我们需要计算 MySQL 中一个表达式的总体标准方差。**variation()**函数可以在 MySQL 中用于此目的。如果在给定的表达式中没有找到匹配的行，则返回空值。

**语法:**

```sql
VARIANCE(expr);
```

**参数:**此方法只接受一个参数。

*   **Expression:** The input expression from which we want to calculate the standard variance.

**返回:**返回总体标准方差。

**示例-1 :**

使用方差函数从给定的 StudentMarks 表中找到 sub1mark 列的标准方差。

**创建学生标记表:**

```sql
CREATE TABLE StudentMarks
(
StudentId INT AUTO_INCREMENT,  
StudentName VARCHAR(100) NOT NULL,
Roll INT NOT NULL,
Sub1Mark INT NOT NULL,
Sub2Mark INT NOT NULL,
Sub3Mark INT NOT NULL,
TotalMarks INT NOT NULL,
PRIMARY KEY(StudentId )
);
```

**将数据插入表格:**

```sql
INSERT INTO StudentMarks
(StudentName, Roll, Sub1Mark, Sub2Mark, Sub3Mark,  TotalMarks)
VALUES
('Amit Jana', 10100, 85, 80, 95, 260),
('Labanya Mallick', 11000, 81, 89, 95, 265),
('Virat Sharma', 12000, 75, 83, 90, 248),
('Sayani Samanta', 13000, 95, 90, 99, 284),
('Riyanka Panda', 14000, 70, 87, 88, 245), 
('Ritika Shah', 15000, 78, 89, 90, 257);
```

要验证是否使用了以下命令，如下所示。

```sql
SELECT  * from StudentMarks;
```

**输出:**

<figure class="table">sub 1 mark

|  | student | [Student name] | 【滚】 | 转向夏尔马 | 【12000】 | 【75】 | 【83】 | 【90】 | 【248】 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

</figure>

现在我们要找到 sub1mark 列的标准方差。

```sql
SELECT  VARIANCE(Sub1Mark) as Sub1Variance 
FROM StudentMarks;
```

**输出:**

<figure class="table">T5】

| sub1 variation |
| --- |
| 62.888888888891 |

</figure>

**示例-2**

现在我们要找到总分栏的标准方差。

```sql
SELECT  VARIANCE(TotalMarks) as VarianceOfTotalMarks 
FROM StudentMarks;
```

**输出:**

<figure class="table">T2】163.1388888877T4

|  |
| --- |

</figure>

**示例-3 :** 在本例中，我们将找到在公司“中航公司”工作的员工收入的总体标准方差，以演示如何创建一个名为 EmloyeeDetails 的表。

```sql
CREATE TABLE EmployeeDetails(

Employee_Id INT AUTO_INCREMENT,  
Employee_Name VARCHAR(100) NOT NULL,
Working_At VARCHAR(20) NOT NULL,
Work_Location  VARCHAR(20) NOT NULL,
Joining_Date DATE NOT NULL,
Annual_Income INT  NOT NULL,
PRIMARY KEY(Employee_Id )
);
```

将数据插入表中:

```sql
INSERT INTO  
EmployeeDetails(Employee_Name, Working_At, Work_Location, Joining_Date, Annual_Income )

VALUES
('Amit Khan', 'XYZ Digital', 'Kolkata', '2019-10-06', 350000 ),
('Shreetama Pal', 'ABC Corp.', 'Kolkata', '2018-12-16', 500000 ),
('Aniket Sharma', 'PQR Soln.', 'Delhi', '2020-01-11', 300000 ),
('Maitree Jana', 'XYZ Digital', 'Kolkata', '2019-05-01', 400000 ),
('Priyanka Ojha', 'ABC Corp.', 'Delhi', '2019-02-13', 350000 ),
('Sayani Mitra', 'XYZ Digital', 'Kolkata', '2019-09-15', 320000 ),
('Nitin Dey', 'PQR Soln.', 'Delhi', '2019-10-06', 250000 ),
('Sujata Samanta', 'PQR Soln.', 'Kolkata', '2020-10-06', 350000 ),
('Sudip Majhi', 'ABC Corp.', 'Delhi', '2018-10-30', 600000 ),
('Sanjoy Kohli', 'XYZ Digital', 'Delhi', '2019-04-18', 450000 ) ;
```

要验证是否使用了以下命令，如下所示。

```sql
Select * FROM EmployeeDetails;
```

**输出:**

<figure class="table">T19】1T21】阿米特汗 T27】2019-10-06 T61T69】2019-05-01T71】400000【t00 T129T131】9T133【苏迪普·马希】T134

| 员工标识 | 员工姓名 | 工作时间 | 工作地点 | 加入日期 | 年收入 |
| --- | --- | --- | --- | --- | --- |
| Numbers XYZ | Calcutta | Delhi | 2020-01-11 | Three hundred thousand |
| four | Mai Rui Jia na | Digital XYZ | Calcutta | Delhi | 2019-10-06 | 250,000 |
| eight | Suta Samanta | PQR· Soren. | Calcutta | 2020-10-06 | Three hundred and fifty thousand |
| Zhonghang company | Delhi | 2018-10-30 | Sixty-six |

</figure>

现在，我们将找到在“ABC 公司”工作的员工年收入的总体标准方差

**输出:**

<figure class="table">

| 公司名称 |  |
| --- | --- |
| 中航集团 | 1055555555.55557 |

</figure>