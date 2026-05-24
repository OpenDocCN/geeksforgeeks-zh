# MySQL中的`STDDEV_SAMP()`函数

> 原文：[https://www.geeksforgeeks.org/stddev_samp-function-in-mysql/](https://www.geeksforgeeks.org/stddev_samp-function-in-mysql/)

`STDDEV_SAMP()`函数用于计算一个表达式的样本标准差。

## 语法

```sql
STDDEV_SAMP(expr);
```

## 参数

此方法只接受一个参数。

*   **表达式**：我们要从中计算样本标准偏差的输入表达式。

## 返回

返回总体标准差。

## 示例-1

使用`STDDEV_SAMP()`函数从给定的玩家表中查找`RunScored`列的样本标准偏差。

### 创建玩家表

```sql
CREATE TABLE Player  
(
PlayerId INT AUTO_INCREMENT,  
PlayerName VARCHAR(100) NOT NULL,
RunScored INT NOT NULL,
WicketsTaken INT NOT NULL,
PRIMARY KEY(PlayerId)
);
```

### 将数据插入表中

```sql
INSERT INTO Player  
(PlayerName, RunScored,  WicketsTaken )
VALUES
('KL Rahul', 52, 0 ),
('Hardik Pandya', 30, 1 ),
('Ravindra Jadeja', 18, 2 ),
('Washington Sundar', 10, 1),
('D Chahar', 11, 2 ),  
('Mitchell Starc', 0, 3);
```

要验证是否使用了以下命令，如下所示。

```sql
SELECT  * from Player ;
```

**输出:**

| PlayerId | PlayerName | RunScored | WicketsTaken |
| --- | --- | --- | --- |
| 1 | KL Rahul | 52 | 0 |
| 2 | Hardik Pandya | 30 | 1 |
| 3 | Ravindra Jadeja | 18 | 2 |
| 4 | Washington Sundar | 10 | 1 |
| 5 | D Chahar | 11 | 2 |
| 6 | Mitchell Starc | 0 | 3 |

现在我们要找到`RunScored`列的样本标准差。

```sql
SELECT  STDDEV_SAMP(RunScored ) as Samp_Standard_Deviation  
FROM Player ;
```

**输出:**

| Samp_Standard_Deviation |
| --- |
| 18.486932321687846 |

## 示例-2

现在我们来找`WicketsTaken`列的样本标准差。

```sql
SELECT  STDDEV_SAMP(WicketsTaken) as Samp_Std_Dev_Wickets    
FROM Player ;
```

**输出:**

| Samp_Std_Dev_Wickets |
| --- |
| 1.0488088481701516 |

## 示例-3

在本例中，我们将找到在“ABC Corp.”工作的员工收入的样本标准差，以演示如何创建一个名为`EmployeeDetails`的表。

### 创建表

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

### 向表中插入数据

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

| Employee_Id | Employee_Name | Working_At | Work_Location | Joining_Date | Annual_Income |
| --- | --- | --- | --- | --- | --- |
| 1 | Amit Khan | XYZ Digital | Kolkata | 2019-10-06 | 350000 |
| 2 | Shreetama Pal | ABC Corp. | Kolkata | 2018-12-16 | 500000 |
| 3 | Aniket Sharma | PQR Soln. | Delhi | 2020-01-11 | 300000 |
| 4 | Maitree Jana | XYZ Digital | Kolkata | 2019-05-01 | 400000 |
| 5 | Priyanka Ojha | ABC Corp. | Delhi | 2019-02-13 | 350000 |
| 6 | Sayani Mitra | XYZ Digital | Kolkata | 2019-09-15 | 320000 |
| 7 | Nitin Dey | PQR Soln. | Delhi | 2019-10-06 | 250000 |
| 8 | Sujata Samanta | PQR Soln. | Kolkata | 2020-10-06 | 350000 |
| 9 | Sudip Majhi | ABC Corp. | Delhi | 2018-10-30 | 600000 |
| 10 | Sanjoy Kohli | XYZ Digital | Delhi | 2019-04-18 | 450000 |

现在我们要找出在“ABC Corp.”工作的员工年收入的总体标准偏差。

```sql
SELECT  'ABC Corp.' AS 'Company_Name',
STDDEV_SAMP(Annual_Income) as StdDevOfAnnualIncome  
FROM EmployeeDetails where WORKING_AT = 'ABC Corp.';
```

**输出:**

| Company_Name | StdDevOfAnnualIncome |
| --- | --- |
| ABC Corp. | 125830.57392117917 |