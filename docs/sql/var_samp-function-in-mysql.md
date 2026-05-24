# MySQL 中的 VAR_SAMP()函数

> 原文:[https://www.geeksforgeeks.org/var_samp-function-in-mysql/](https://www.geeksforgeeks.org/var_samp-function-in-mysql/)

**MySQL 中的 VAR_SAMP()** 函数用于计算一个表达式的样本方差。

**语法:**

```sql
VAR_SAMP(expr);
```

**参数:**该方法只接受一个参数。

*   **表达式:**我们要从中计算样本方差的输入表达式。

**返回:**返回样本方差。

**示例-1 :**
使用 VAR_SAMP 函数从给定的玩家表中找到 RunScored 列的样本方差。

**创建玩家表:**

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

**将数据插入表中:**

```sql
INSERT INTO Player 
(PlayerName, RunScored,  WicketsTaken )
VALUES
('
KL Rahul', 52, 0 ),
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

| 球员 | 玩家名 | 修复 | WICKETSTAKEN |
| --- | --- | --- | --- |
| one | 拉胡尔 | fifty-two | Zero |
| Two | 哈迪克·潘迪亚 | Thirty | one |
| three | Ravindra Jadeja | Eighteen | Two |
| four | 华盛顿圣达 | Ten | one |
| five | d 查哈尔 | Eleven | Two |
| six | 米切尔星 | Zero | three |

现在我们要找到运行得分列的样本方差。

```sql
SELECT  VAR_SAMP(RunScored ) as Run_Variance 
FROM Player ;

```

**输出:**

| 运行 _ 方差 |
| --- |
| 341.7666666666667 |

**示例-2 :**
现在我们要找到 WicketsTaken 列的样本方差。

```sql
SELECT  VAR_SAMP(WicketsTaken) as Wicket_Variance 
FROM Player ;

```

**输出:**

| WICKET_VARIANCE |
| --- |
| One point one |

**示例-3 :**
在本例中，我们将找到在公司“PQR 索恩”工作的员工收入的样本方差为了演示，创建一个名为 EmloyeeDetails 的表。

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

向表中插入数据:

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

| 员工标识 | 员工姓名 | 工作时间 | 工作地点 | 加入日期 | 年收入 |
| --- | --- | --- | --- | --- | --- |
| one | 阿米尔汗 | XYZ 数码 | 加尔各答 | 2019-10-06 | Three hundred and fifty thousand |
| Two | 什里塔玛·帕尔 | 美国广播公司 | 加尔各答 | 2018-12-16 | Five hundred thousand |
| three | 阿尼克·夏尔马 | PQR Soln . | 德里 | 2020-01-11 | Three hundred thousand |
| four | maitree jana | XYZ 数码 | 加尔各答 | 2019-05-01 | Four hundred thousand |
| five | 普里扬卡·奥哈 | 美国广播公司 | 德里 | 2019-02-13 | Three hundred and fifty thousand |
| six | 萨亚尼·米特拉 | XYZ 数码 | 加尔各答 | 2019-09-15 | Three hundred and twenty thousand |
| seven | 尼廷·戴伊 | PQR Soln . | 德里 | 2019-10-06 | Two hundred and fifty thousand |
| eight | 你也一样 | PQR Soln . | 加尔各答 | 2020-10-06 | Three hundred and fifty thousand |
| nine | 阿伦 m | 美国广播公司 | 德里 | 2018-10-30 | Six hundred thousand |
| Ten | 桑乔伊·科里 | XYZ 数码 | 德里 | 2019-04-18 | Four hundred and fifty thousand |

现在，我们将找到在“PQR 索恩”工作的员工的年收入差异样本

```sql
SELECT 'PQR Soln.' AS 'Company_Name',
VAR_SAMP(Annual_Income) as VarianceOfAnnualIncome  
FROM EmployeeDetails where WORKING_AT = 'PQR Soln.';

```

**输出:**

| 公司名称 | 变量 |
| --- | --- |
| PQR Soln . | Two billion five hundred million |