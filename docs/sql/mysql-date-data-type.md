# MySQL 日期数据类型

> 原文:[https://www.geeksforgeeks.org/mysql-date-data-type/](https://www.geeksforgeeks.org/mysql-date-data-type/)

**MySQL 日期数据类型:**

MySQL 支持多种数据类型。其中有时我们需要取 DATE 数据类型来存储数据值。DATE 类型用于有日期部分但没有时间部分的值。它以' YYYY-MM-DD '格式显示日期值。我们可以存储给定范围' 1000-01-01 '到' 9999-12-31 '内的任何日期值。

**语法:**

```sql
Variable_Name DATE
```

以下示例将说明我们如何在变量中使用日期数据类型。

**例 1 :**

**创建学生详细信息表****—**
它由学生身份证、名字、姓氏、出生日期、班级、联系人详细信息列组成。其中出生日期列的数据类型为日期。

```sql
CREATE TABLE StudentDetails (
   Student_Id INT AUTO_INCREMENT,       
   First_name VARCHAR (100) NOT NULL,       
   Last_name VARCHAR (100) NOT NULL,      
   Date_Of_Birth DATE NOT NULL,       
   Class VARCHAR (10) NOT NULL,       
   Contact_Details BIGINT NOT NULL,      
   PRIMARY KEY(Student_Id )       
);
```

**将数据插入表格–**

```sql
INSERT INTO     
StudentDetails(First_name , Last_name , Date_Of_Birth , Class, Contact_Details)    
VALUES 
('Amit', 'Jana', '2004-12-22', 'XI', 1234567890),    
('Manik', 'Aggarwal', '2006-07-04', 'IX', 1245678998),    
('Nitin', 'Das', '2005-03-14', 'X', 2245664909),    
('Priya', 'Pal', '2007-07-24', 'VIII', 3245642199),    
('Biswanath', 'Sharma', '2005-11-11', 'X', 2456789761),    
('Mani', 'Punia', '2006-01-20', 'IX', 3245675421),    
('Pritam', 'Patel', '2008-01-04', 'VII', 3453415421),    
('Sayak', 'Sharma', '2007-05-10', 'VIII' , 1214657890);
```

**使用如下命令进行验证。**

```sql
SELECT * FROM StudentDetails ;
```

**输出:**

<figure class="table">【pal】

|  | [Student id] | 【名字】 | 【姓氏】 | [date of birth] |  | 【2245664909】 |
| --- | --- | --- | --- | --- | --- | --- |
|  | 【Priya】 |  | 【T1116】【343 411】【T1117】【T1120】 |  |
| --- | --- | --- | --- | --- |

</figure>

因此，我们已经成功地在出生日期列中存储了日期数据类型。

**例 2 :**

**创建产品详细信息表****—**
它由产品标识、产品名称和制造日期列组成，其中制造日期列的数据类型为日期。

```sql
CREATE TABLE ProductDetails(
ProductId INT NOT NULL,
ProductName VARCHAR(20) NOT NULL,
Manufactured_On DATE NOT NULL,
PRIMARY KEY(ProductId)
);
```

**将数据插入表中–**
CURRENTDATE 函数用于在 Manufactured_On 列中赋值。CURRENTDATE 函数的返回数据类型是 DATE。

```sql
INSERT INTO  
ProductDetails(ProductId, ProductName, Manufactured_On)
VALUES
(11001, 'ASUS X554L', CURRENT_DATE()) ;
```

**使用如下命令进行验证。**

```sql
SELECT  * from ProductDetails;
```

**输出:**

<figure class="table">

| 【产品 id】 | 【产品名称】 | 【制造日期】 |
| --- | --- | --- |

</figure>

**例 3 :**

**创建订单表****—**
它由订单号、订单日期、发货日期、发货日期列组成。其中“订单日期”、“发货日期”和“交货日期”列的数据类型为“日期”。

```sql
CREATE TABLE Orders(
   OrderNumber INT AUTO_INCREMENT,
   OrderDate DATE NOT NULL,
   ShippedDate DATE NOT NULL,
   DeliveryDate  DATE NOT NULL,
   PRIMARY KEY(OrderNumber )
);
```

**将数据插入表格–**

```sql
INSERT INTO 
Orders(OrderNumber , OrderDate , ShippedDate  , DeliveryDate )
VALUES 
(1001, '2019-12-21', '2004-12-22', '2019-12-26'),
(1002, '2020-01-21', '2020-01-21', '2020-01-22'),
(1003, '2020-05-01', '2020-05-03', '2020-05-10'),
(1004, '2020-07-31', '2020-08-01', '2020-08-01');
```

**验证使用了如下命令。**

```sql
SELECT * FROM Orders;
```

**输出:**

<figure class="table">

|  | order number | Date of order | delivery date |
| --- | --- | --- | --- |

</figure>