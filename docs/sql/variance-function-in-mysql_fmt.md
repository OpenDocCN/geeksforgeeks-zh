# MySQL 中的方差函数

> 原文: [https://www.geeksforgeeks.org/variance-function-in-mysql/](https://www.geeksforgeeks.org/variance-function-in-mysql/)

有时我们需要计算 MySQL 中一个表达式的总体标准方差。`VARIANCE()`函数可以在 MySQL 中用于此目的。如果在给定的表达式中没有找到匹配的行，则返回空值。

## 语法:

```sql
VARIANCE(expr);
```

## 参数:

此方法只接受一个参数。

*   **Expression:** The input expression from which we want to calculate the standard variance.

## 返回:

返回总体标准方差。

## 示例-1 :

使用方差函数从给定的 `StudentMarks` 表中找到 `Sub1Mark` 列的标准方差。

### 创建学生标记表:

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

### 将数据插入表格:

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

| StudentId | StudentName       | Roll   | Sub1Mark | Sub2Mark | Sub3Mark | TotalMarks |
|-----------|-------------------|--------|----------|----------|----------|------------|
| 1         | Amit Jana         | 10100  | 85       | 80       | 95       | 260        |
| 2         | Labanya Mallick   | 11000  | 81       | 89       | 95       | 265        |
| 3         | Virat Sharma      | 12000  | 75       | 83       | 90       | 248        |
| 4         | Sayani Samanta    | 13000  | 95       | 90       | 99       | 284        |
| 5         | Riyanka Panda     | 14000  | 70       | 87       | 88       | 245        |
| 6         | Ritika Shah       | 15000  | 78       | 89       | 90       | 257        |

现在我们要找到 `Sub1Mark` 列的标准方差。

```sql
SELECT  VARIANCE(Sub1Mark) as Sub1Variance 
FROM StudentMarks;
```

**输出:**

| Sub1Variance          |
|-----------------------|
| 62.888888888891       |

## 示例-2

现在我们要找到总分栏的标准方差。

```sql
SELECT  VARIANCE(TotalMarks) as VarianceOfTotalMarks 
FROM StudentMarks;
```

**输出:**

| VarianceOfTotalMarks  |
|-----------------------|
| 163.1388888877        |

## 示例-3 :

在本例中，我们将找到在公司“中航公司”工作的员工收入的总体标准方差，以演示如何创建一个名为 `EmployeeDetails` 的表。

### 创建表:

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

### 将数据插入表中:

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

| Employee_Id | Employee_Name   | Working_At   | Work_Location | Joining_Date | Annual_Income |
|-------------|-----------------|--------------|---------------|--------------|---------------|
| 1           | Amit Khan       | XYZ Digital  | Kolkata       | 2019-10-06   | 350000        |
| 2           | Shreetama Pal   | ABC Corp.    | Kolkata       | 2018-12-16   | 500000        |
| 3           | Aniket Sharma   | PQR Soln.    | Delhi         | 2020-01-11   | 300000        |
| 4           | Maitree Jana    | XYZ Digital  | Kolkata       | 2019-05-01   | 400000        |
| 5           | Priyanka Ojha   | ABC Corp.    | Delhi         | 2019-02-13   | 350000        |
| 6           | Sayani Mitra    | XYZ Digital  | Kolkata       | 2019-09-15   | 320000        |
| 7           | Nitin Dey       | PQR Soln.    | Delhi         | 2019-10-06   | 250000        |
| 8           | Sujata Samanta  | PQR Soln.    | Kolkata       | 2020-10-06   | 350000        |
| 9           | Sudip Majhi     | ABC Corp.    | Delhi         | 2018-10-30   | 600000        |
| 10          | Sanjoy Kohli    | XYZ Digital  | Delhi         | 2019-04-18   | 450000        |

现在，我们将找到在“ABC 公司”工作的员工年收入的总体标准方差。

```sql
SELECT VARIANCE(Annual_Income) as VarianceOfIncome 
FROM EmployeeDetails 
WHERE Working_At = 'ABC Corp.';
```

**输出:**

| VarianceOfIncome      |
|-----------------------|
| 1055555555.55557      |