# MySQL 中的 LOG10()函数

> 原文:[https://www.geeksforgeeks.org/log10-function-in-mysql/](https://www.geeksforgeeks.org/log10-function-in-mysql/)

**MySQL 中的 LOG10()** 函数用于计算以 10 为底的特定数字的自然对数。该数字必须大于 0，否则将返回空值。

**语法:**

```sql
LOG10(X)
```

**参数:**该方法接受语法中如上所述的一个参数，描述如下:

*   **X–**我们要计算的以 10 为底的对数数值。应该是正数。

**返回:**返回给定数字 x 的自然对数，以 10 为底。

**示例-1 :**
使用 LOG10()函数计算以 10 为底的给定数字的对数。

```sql
SELECT LOG10(1000) AS Log10_Val ;
```

**输出:**

| Log10_Val |
| --- |
| three |

**例-2 :**
使用 LOG10()函数求 0 的对数。

```sql
SELECT LOG10(0) AS Log10_Val ;
```

**输出:**

| Log10_Val |
| --- |
| 空 |

**例-3:**
LOG10 函数也可以用来求一列数据的以 10 为基数的对数值。演示创建一个名为“产品”的表。

```sql
CREATE TABLE Product(
Product_id INT AUTO_INCREMENT,  
Product_name VARCHAR(100) NOT NULL,
Buying_price DECIMAL(13, 2) NOT NULL,
Selling_price DECIMAL(13, 2) NOT NULL,
Service_grade Decimal(6, 2) NOT NULL,
PRIMARY KEY(Product_id)
);
```

**现在向产品表中插入一些数据–**

```sql
INSERT INTO  
Product(Product_name, Buying_price, Selling_price, Service_grade)
VALUES
('Touring Bike', 2019.00, 3009.6, 5.89 ),
('Mountain Bike', 3019.50, 4000.56, 10.00 ),
('Road Bike', 1019.20, 2000.56, -0.89 ),
('Road Bicycle', 1419.50, 1800.56, -1.50 ),
('Racing Bicycle', 3000.50, 4500.56, 5.00) ;
```

**显示产品表中的所有数据–**

```sql
Select * from Product;
```

| 产品标识 | 产品名称 | BUYING_PRICE | 销售价格 | 服务等级 |
| --- | --- | --- | --- | --- |
| one | 旅游自行车 | Two thousand and nineteen | Three thousand and nine point six | Five point eight nine |
| Two | 山地车 | Three thousand and nineteen point five | Four thousand point five six | Ten |
| three | 公路自行车 | One thousand and nineteen point two | Two thousand point five six | -0.89 |
| four | 公路自行车 | One thousand four hundred and nineteen point five | One thousand eight hundred point five six | -1.50 |
| five | 赛车 | Three thousand point five | Four thousand five hundred point five six | Five |

现在，我们将查找 Service_grade 列中所有记录的以 10 为基数的对数值。

```sql
Select Product_id, Product_name, Buying_price, 
Selling_price, Service_grade,
LOG10(Service_grade) AS GRADELOG10  
FROM Product;
```

**输出:**

| 产品标识 | 产品名称 | BUYING_PRICE | 销售价格 | 服务等级 | 十级曲速 10 级曲速 10 级曲速 10 级曲速 10 级曲速 10 级曲速 10 级曲速 10 级曲速 10 级曲速 10 级曲速 10 级曲速 10 级曲速 10 级曲速 |
| --- | --- | --- | --- | --- | --- |
| one | 旅游自行车 | Two thousand and nineteen | Three thousand and nine point six | Five point eight nine | 0.7701152947871016 |
| Two | 山地车 | Three thousand and nineteen point five | Four thousand point five six | Ten | one |
| three | 公路自行车 | One thousand and nineteen point two | Two thousand point five six | -0.89 | 空 |
| four | 公路自行车 | One thousand four hundred and nineteen point five | One thousand eight hundred point five six | -1.50 | 空 |
| five | 赛车 | Three thousand point five | Four thousand five hundred point five six | Five | 0.6989700043360189 |