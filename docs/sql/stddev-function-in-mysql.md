# MySQL 中的 STDDEV()函数

> 原文:[https://www.geeksforgeeks.org/stddev-function-in-mysql/](https://www.geeksforgeeks.org/stddev-function-in-mysql/)

有时我们需要计算 MySQL 中一个表达式的总体标准差。
**【STDDEV()】**函数可以在 MySQL 中用于此目的。如果在给定的表达式中没有找到匹配的行，则返回空值。

**语法:**

```sql
STDDEV(expr);
```

**参数:**此方法只接受一个参数。

*   **表达式:**我们要从中计算标准差的输入表达式。

**返回:**返回总体标准差。

**示例-1 :**
使用 STDDEV 函数从给定的 StudentMarks 表中找到 sub1mark 列的标准偏差。

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

向表中插入数据:

```sql
INSERT INTO StudentMarks
(StudentName, Roll, Sub1Mark, Sub2Mark, Sub3Mark, TotalMarks)
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

| 学生证 | 学生姓名 | 卷 | SUB1MARK | SUB2MARK | SUB3MARK | 总分数 |
| --- | --- | --- | --- | --- | --- | --- |
| one | 就像约翰娜一样 | Ten thousand one hundred | eighty-five | Eighty | Ninety-five | Two hundred and sixty |
| Two | 拉班雅·马里克 | Eleven thousand | Eighty-one | eighty-nine | Ninety-five | Two hundred and sixty-five |
| three | Virat Sharma | Twelve thousand | Seventy-five | Eighty-three | Ninety | Two hundred and forty-eight |
| four | 萨尼·萨曼塔 | Thirteen thousand | Ninety-five | Ninety | Ninety-nine | Two hundred and eighty-four |
| five | 里亚卡熊猫 | Fourteen thousand | Seventy | Eighty-seven | Eighty-eight | Two hundred and forty-five |
| six | 里蒂卡·沙阿 | Fifteen thousand | seventy-eight | eighty-nine | Ninety | Two hundred and fifty-seven |

现在我们要找到 sub1mark 列的标准差。

```sql
SELECT  STDDEV(Sub1Mark) as Sub1StandardDeviation  
FROM StudentMarks;
```

**输出:**

| sub1s 标准偏差 |
| --- |
| 7.930251502246881 |

**示例-2**

现在我们要找到总分栏的总体标准差。

```sql
SELECT  STDDEV(TotalMarks) as StdDevOfTotalMarks  
FROM StudentMarks;
```

**输出:**

| STDDEVOFTOTALMARKS |
| --- |
| 12.772583485297279 |

**示例-3 :** 在本例中，我们将找到在“XYZ 数字”公司工作的员工收入的总体标准差。为了演示，创建一个名为**的表格。**

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

现在我们要找出在“XYZ 数字”工作的员工年收入的总体标准差。

```sql
SELECT  STDDEV(Annual_Income) as StdDevOfAnnualIncome  
FROM EmployeeDetails where WORKING_AT = 'XYZ Digital';

```

**输出:**

| STDDEVOFANNUALINCOME |
| --- |
| 49497.474683058324 |