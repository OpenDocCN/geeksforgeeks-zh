# MySQL 中的 BIT_OR()函数

> 原文:[https://www.geeksforgeeks.org/bit_or-function-in-mysql/](https://www.geeksforgeeks.org/bit_or-function-in-mysql/)

**MySQL 中的 BIT_OR()** 函数用于返回给定表达式中所有位的按位 OR。它首先将所有十进制值转换为二进制值，然后对这些二进制值执行按位“或”运算。

**语法:**

```sql
BIT_OR(expr)
```

**参数:**此方法只接受一个参数。

*   **表达式–**
    输入表达式，我们要在该表达式上应用位或函数。

**返回:**返回给定表达式中所有位的按位或。

**示例-1 :**
为了演示 BIT_OR 函数的工作原理，我们必须首先创建一个名为 EmployeeDetails 的表。

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

现在，将值插入表中–

```sql
INSERT INTO EmployeeDetails (Employee_Name, Working_At, 
Work_Location, Joining_Date, Annual_Income)
VALUES
('Amit Khan', 'XYZ Digital', 'Kolkata', '2019-10-06', 350000),
('Shreetama Pal', 'ABC Corp.', 'Kolkata', '2018-12-16', 500000),
('Aniket Sharma', 'PQR Soln.', 'Delhi', '2020-01-11', 300000),
('Maitree Jana', 'XYZ Digital', 'Kolkata', '2019-05-01', 400000),
('Priyanka Ojha', 'ABC Corp.', 'Delhi', '2019-02-13', 350000),
('Sayani Mitra', 'XYZ Digital', 'Kolkata', '2019-09-15', 320000),
('Nitin Dey', 'PQR Soln.', 'Delhi', '2019-10-06', 250000),
('Sujata Samanta', 'PQR Soln.', 'Kolkata', '2020-10-06', 350000),
('Sudip Majhi', 'ABC Corp.', 'Delhi', '2018-10-30', 600000),
('Sanjoy Kohli', 'XYZ Digital', 'Delhi', '2019-04-18', 450000);
```

要验证是否使用了以下命令–

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

现在，我们将从雇员详细信息表中找到公司所有雇员年收入的位或。

```sql
SELECT Working_At, BIT_OR(Annual_Income) AS BITORINCOME 
FROM EmployeeDetails group by Working_At;
```

**输出:**

| 工作时间 | BITORINCOME |
| --- | --- |
| XYZ 数码 | Five hundred and twenty-four thousand two hundred and seventy-two |
| 美国广播公司 | One million forty-six thousand five hundred and twelve |
| PQR Soln . | Five hundred and fourteen thousand and thirty-two |

**示例-2 :**
现在我们将从 EmployeeDetails 表中找到所有员工年收入的 BIT_OR。

```sql
SELECT Work_Location, BIT_OR(Annual_Income) AS BITORINCOME 
FROM EmployeeDetails 
Group By Work_Location;
```

**输出:**

| 工作地点 | BITORINCOME |
| --- | --- |
| 加尔各答 | Five hundred and twenty-four thousand two hundred and eight |
| 德里 | One million forty-eight thousand five hundred and sixty |

**示例-3 :**
首先创建学生成绩表–

```sql
CREATE TABLE StudentMarks(
StudentId INT AUTO_INCREMENT,  
StudentName VARCHAR(100) NOT NULL,
Class VARCHAR(20) NOT NULL,
Roll INT NOT NULL,
Sub1Mark INT NOT NULL,
Sub2Mark INT NOT NULL,
Sub3Mark INT NOT NULL,
TotalMarks INT NOT NULL,
PRIMARY KEY(StudentId)
);
```

将数据插入表格–

```sql
INSERT INTO StudentMarks
(StudentName, Class, Roll, Sub1Mark, 
Sub2Mark, Sub3Mark, TotalMarks)
VALUES
('Amit Jana', 'V', 10100, 85, 80, 95, 260),
('Labanya Mallick', 'VI', 11000, 81, 89, 95, 265),
('Virat Sharma', 'VI', 12000, 75, 83, 90, 248),
('Sayani Samanta', 'V', 13000, 95, 90, 99, 284),
('Riyanka Panda', 'V', 14000, 70, 87, 88, 245),  
('Ritika Shah', 'VI', 15000, 78, 89, 90, 257);
```

要验证是否使用了以下命令–

```sql
SELECT  * From StudentMarks;
```

**输出:**

| 学生证 | 学生姓名 | 班级 | 卷 | SUB1MARK | SUB2MARK | SUB3MARK | 总分数 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| one | 就像约翰娜一样 | V | Ten thousand one hundred | eighty-five | Eighty | Ninety-five | Two hundred and sixty |
| Two | 拉班雅·马里克 | 我们吗 | Eleven thousand | Eighty-one | eighty-nine | Ninety-five | Two hundred and sixty-five |
| three | Virat Sharma | 我们吗 | Twelve thousand | Seventy-five | Eighty-three | Ninety | Two hundred and forty-eight |
| four | 萨尼·萨曼塔 | V | Thirteen thousand | Ninety-five | Ninety | Ninety-nine | Two hundred and eighty-four |
| five | 里亚卡熊猫 | V | Fourteen thousand | Seventy | Eighty-seven | Eighty-eight | Two hundred and forty-five |
| six | 里蒂卡·沙阿 | 我们吗 | Fifteen thousand | seventy-eight | eighty-nine | Ninety | Two hundred and fifty-seven |

现在我们将从学生成绩表中找到所有学生班级总成绩的位或。

```sql
SELECT Class, BIT_OR(TotalMarks) AS BITORMARKS 
FROM StudentMarks 
Group By Class;
```

**输出:**

| 班级 | BITORMARKS |
| --- | --- |
| V | Five hundred and nine |
| 我们吗 | Five hundred and five |