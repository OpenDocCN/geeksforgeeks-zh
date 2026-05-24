# MySQL 中的 LOG2()函数

> 原文:[https://www.geeksforgeeks.org/log2-function-in-mysql/](https://www.geeksforgeeks.org/log2-function-in-mysql/)

在本文中，我们将介绍 LOG2()函数，这意味着它将计算以 2 为底的特定数字的对数。

先决条件:[日志功能](https://www.geeksforgeeks.org/log-function-in-mysql/#:~:text=LOG()%20function%20in%20MySQL%20is%20used%20to%20calculate%20the,Otherwise%20it%20will%20return%20NULL.)

**LOG2()** [函数在 MySQL 中](https://www.geeksforgeeks.org/sql-functions-aggregate-scalar-functions/)用来计算以 2 为基数的特定数字的自然对数。数字必须是> 0，否则返回空值。

**语法:**

```sql
LOG2( X )

```

**参数:**
LOG2()函数接受一个参数，描述如下。

*   **X–**我们要计算的以 2 为底的对数数值。应该是正数。

**返回:**
返回给定数字 x 的自然对数，以 2 为底。

**示例-1 :**
使用 LOG2()函数对给定的以 2 为底的数进行对数运算。

```sql
SELECT LOG2(16) AS Log2_Val;

```

**输出:**

| Log2_Val |
| --- |
| four |

**例-2 :**
使用 LOG2()函数求 0 的对数。

```sql
SELECT LOG2(0) AS Log2_Val;

```

**输出:**

| Log2_Val |
| --- |
| 空 |

**例-3:**
LOG2 函数也可以用来求列数据以 2 为基数的对数值。为了演示，创建一个名为**产品**的表格。

```sql
CREATE TABLE Product
(
    Product_id INT AUTO_INCREMENT,  
    Product_name VARCHAR(100) NOT NULL,
    Buying_price DECIMAL(13,2) NOT NULL,
    Selling_price DECIMAL(13,2) NOT NULL,
    Service_grade Decimal(6,2) NOT NULL,
    PRIMARY KEY(Product_id)

);

```

**现在向产品表中插入一些数据:**

```sql
INSERT INTO Product
(Product_name, Buying_price, Selling_price, Service_grade)
VALUES
    ('Touring Bike' ,2019.00 ,3009.6 ,0.89 ) ,
    ('Mountain Bike' ,3019.50 ,4000.56 ,1.00 ) ,
    ('Road Bike' ,1019.20 ,2000.56 ,-0.89 ) ,
    ('Road Bicycle',1019.50 ,1500.56 ,-1.50 ) ,
    ('Racing Bicycle',3019.50 ,4000.56 ,2.00) ;

```

**显示产品表中的所有数据:**

```sql
Select * from Product;

```

| 产品 id | 产品名称 | 购买价格 | 销售价格 | 服务等级 |
| --- | --- | --- | --- | --- |
| one | 旅游自行车 | Two thousand and nineteen | Three thousand and nine point six | Zero point eight nine |
| Two | 山地车 | Three thousand and nineteen point five | Four thousand point five six | One |
| three | 公路自行车 | One thousand and nineteen point two | Two thousand point five six | -0.89 |
| four | 公路自行车 | One thousand and nineteen point five | One thousand five hundred point five six | -1.50 |
| five | 赛车 | Three thousand and nineteen point five | Four thousand point five six | Two |

现在，我们将找到 Service_grade 列中所有记录的以 2 为基数的对数值。

```sql
        Select 
    Product_id,  
    Product_name,  
    Buying_price,  
    Selling_price,  
    Service_grade,
    LOG2(Service_grade) AS GRADELOG2  
        FROM Product;

```

**输出:**

| 产品 id | 产品名称 | 购买价格 | 销售价格 | 服务等级 | 度 2 |
| --- | --- | --- | --- | --- | --- |
| one | 旅游自行车 | Two thousand and nineteen | Three thousand and nine point six | Zero point eight nine | -0.16812275880832692 |
| Two | 山地车 | Three thousand and nineteen point five | 4000.56  | One | Zero |
| three | 公路自行车 | One thousand and nineteen point two | Two thousand point five six | -0.89 | 空 |
| four | 公路自行车 | One thousand and nineteen point five | One thousand five hundred point five six | -1.50 | 空 |
| five | 赛车 | Three thousand and nineteen point five | Four thousand point five six | Two | one |