# MySQL 中的 BIT_AND()函数

> 原文:[https://www.geeksforgeeks.org/bit_and-function-in-mysql/](https://www.geeksforgeeks.org/bit_and-function-in-mysql/)

**BIT_AND() :**

MySQL 中的这个函数用于返回给定表达式中所有位的按位与。它首先将所有十进制值转换为二进制值，然后对这些二进制值执行按位“与”运算。

**语法:**

```sql
BIT_AND(expr)
```

**参数:**

此方法只接受一个参数。

*   **Expression–** We want to apply the input expression of the BIT_AND function to it.

**返回:**

它返回给定表达式中所有位的按位“与”。

**示例-1 :**

在表的列中使用位与函数

**创建员工表–**

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

**将数值插入表格–**

```sql
INSERT INTO  
EmployeeDetails(Employee_Name , Working_At, Work_Location, Joining_Date, Annual_Income )

VALUES
('Amit Khan' , 'XYZ Digital' , 'Kolkata' ,'2019-10-06' , 350000 ) ,
('Shreetama Pal' , 'ABC Corp.' , 'Kolkata' ,'2018-12-16' , 500000 )  ,
('Aniket Sharma' , 'PQR Soln.' , 'Delhi' , '2020-01-11' ,300000 ) ,
('Maitree Jana' , 'XYZ Digital' , 'Kolkata' ,'2019-05-01' , 400000 ) ,
('Priyanka Ojha' , 'ABC Corp.' , 'Delhi' ,'2019-02-13' , 350000 ) ,
('Sayani Mitra' , 'XYZ Digital' , 'Kolkata' ,'2019-09-15' , 320000 ) ,
('Nitin Dey' , 'PQR Soln.' , 'Delhi' ,'2019-10-06' , 250000 ) ,
('Sujata Samanta' , 'PQR Soln.' , 'Kolkata' ,'2020-10-06' , 350000 ) ,
('Sudip Majhi' , 'ABC Corp.' , 'Delhi' ,'2018-10-30' , 600000 ) ,
('Sanjoy Kohli' , 'XYZ Digital' ,'Delhi' ,'2019-04-18' , 450000 ) ;
```

表格将如下所示。

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

现在我们将从“员工详细信息”表中找到公司所有员工年收入的位与。

```sql
SELECT Working_At, BIT_AND(Annual_Income) AS BITANDINCOME
FROM employeedetails group by Working_At;
```

**输出:**

<figure class="table">

| work _ AT | BITANDINCOME |
| --- | --- |
| Numbers XYZ | Two hundred and sixty-two thousand one hundred and forty-four |
| 美国广播公司。 | Sixty-five thousand seven hundred and ninety-two |
| PQR Soren. | Four thousand and ninety-six |

</figure>

**示例-2 :**

现在我们将从“员工详细信息”表中找到所有员工年收入的位与。

```sql
SELECT Work_Location, BIT_AND(Annual_Income) AS BITANDINCOME
FROM EmployeeDetails group by  Work_Location;
```

**输出:**

<figure class="table">

|  | Work _ location | bitline 怎么说 |
| --- | --- | --- |
| 【加尔各答】 |  |

</figure>

**示例-3 :**

**创建学生表–**

```sql
CREATE TABLE StudentMarks
(
StudentId INT AUTO_INCREMENT,  
StudentName VARCHAR(100) NOT NULL,
Class VARCHAR(20) NOT NULL,
Roll INT NOT NULL,
Sub1Mark INT NOT NULL,
Sub2Mark INT NOT NULL,
Sub3Mark INT NOT NULL,
TotalMarks INT NOT NULL,
PRIMARY KEY(StudentId )
);
```

**将数据插入表格–**

```sql
INSERT INTO StudentMarks
(StudentName, Class, Roll, Sub1Mark, Sub2Mark, Sub3Mark, TotalMarks)
VALUES
('Amit Jana', 'V', 10100, 85, 80, 95, 260),
('Labanya Mallick', 'VI', 11000, 81, 89, 95, 265),
('Virat Sharma', 'VI', 12000, 75, 83, 90, 248),
('Sayani Samanta', 'V', 13000, 95, 90, 99, 284),
('Riyanka Panda', 'V', 14000, 70, 87, 88, 245),  
('Ritika Shah', 'VI', 15000, 78, 89, 90, 257);
```

表格如下。

```sql
SELECT  * from StudentMarks;
```

**输出:**

<figure class="table">滚动

|  | [Students] | [Student name] | [class] | 【265】 |
| --- | --- | --- | --- | --- |
| 

&#124; 的你好 Sharma &#124; 【VI】 &#124;  &#124; 【75】 &#124; 【245】【T1110】【T1112】 &#124;  &#124;

 |
| --- |

</figure>

现在我们将从“学生分数”表中找到所有学生班级总分数的位与。

```sql
SELECT Class, BIT_AND(TotalMarks) AS BITANDMARKS
FROM StudentMarks group by Class;
```

**输出:**

<figure class="table">

| kind | 【位元】 |
| --- | --- |
|  |  |

</figure>