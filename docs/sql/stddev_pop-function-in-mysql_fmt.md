# MySQL 中的 `STDDEV_POP()` 函数

> 原文: [https://www.geeksforgeeks.org/stddev_pop-function-in-mysql/](https://www.geeksforgeeks.org/stddev_pop-function-in-mysql/)

## 函数介绍
`STDDEV_POP()` 是 MySQL 中的一个函数，用来计算一个表达式的总体标准差。

## 语法
```sql
STDDEV_POP(expr);
```

## 参数
此方法只接受一个参数。

*   `expr` – 输入表达式，我们要从中计算总体标准差。

## 返回
返回总体标准差。

## 示例-1
使用 `STDDEV_POP` 函数从给定的玩家表中找到 `RunScored` 列的总体标准差。

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

现在，我们要找到运行得分列的总体标准差。
```sql
SELECT  STDDEV_POP(RunScored ) 
as Pop_Standard_Deviation 
FROM Player ;
```

**输出:**

| Pop_Standard_Deviation |
| --- |
| 16.87618308609964 |

## 示例-2
现在，我们要找到 `WicketsTaken` 列的人口标准差。
```sql
SELECT  STDDEV_POP(WicketsTaken) 
as Pop_Std_Dev_Wickets   
FROM Player ;
```

**输出:**

| Pop_Std_Dev_Wickets |
| --- |
| 0.9574271077563381 |

## 示例-3
在本例中，我们将找到在“加尔各答”工作的员工收入的总体标准偏差，以演示如何创建一个名为 `EmployeeDetails` 的表。

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

### 将数据插入表中
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

现在，我们要找出工作地点在“加尔各答”的员工年收入的人口标准差。
```sql
SELECT  'Kolkata' AS 'Work_Location',
STDDEV_POP(Annual_Income) as PopStdDevOfAnnualIncome  
FROM EmployeeDetails where Work_Location = 'Kolkata';
```

**输出:**

| Work_Location | PopStdDevOfAnnualIncome |
| --- | --- |
| Kolkata | 63435.006108614834 |