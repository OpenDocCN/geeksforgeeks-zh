# MySQL 中的 LN()函数

> 原文:[https://www.geeksforgeeks.org/ln-function-in-mysql/](https://www.geeksforgeeks.org/ln-function-in-mysql/)

**LN()函数:**
是 MySQL 中的[函数，用于计算以 e 为基数的特定数字的自然对数，该数字必须大于 0，否则将返回 NULL。](https://www.geeksforgeeks.org/sql-functions-aggregate-scalar-functions/)

**语法:**

```sql
LN(X)
```

**参数:**
LN()函数接受语法中如上所述的一个参数，描述如下。

**X–**我们要计算其以 e 为底的对数值的数字。应该是正数。

**返回:**
返回给定数字 x 的自然对数，以 e 为底

**示例-1 :**
使用 LN()函数，以 e 为底数的给定数字的对数。

```sql
SELECT LN(1000) AS Ln_Val ;

```

**输出:**

| LN_VAL |
| --- |
| 6.907755278982137 |

**例-2 :**
使用 LN()函数求 0 的对数。

```sql
SELECT LN(0) AS Ln_Val ;

```

**输出:**

| LN_VAL |
| --- |
| 空 |

**例-3:**
LN 函数也可以用来求一列数据的以 e 为基数的对数值。演示创建一个名为“产品”的表。

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

**插入产品表:**
现在向产品表插入一些数据–

```sql
INSERT INTO  
Product(Product_name, Buying_price, Selling_price, Service_grade)
VALUES
('Touring Bike', 20000.00, 30050.00, 4.17 ),
('Mountain Bike', 30005.50, 40000.56, 10.00 ),
('Road Bike', 10000.20, 21000.56, -3.59 ),
('Road Bicycle', 15200.50, 18000.00, -0.50 ),
('Racing Bicycle', 30500.50, 45000.00, 3.00) ;

```

**从表中读取数据:**
显示产品表中的所有数据–

```sql
Select * from Product;

```

**输出:**

| 产品标识 | 产品名称 | BUYING_PRICE | 销售价格 | 服务等级 |
| --- | --- | --- | --- | --- |
| one | 旅游自行车 | Twenty thousand | Thirty thousand and fifty | 4.17  |
| Two | 山地车 | Thirty thousand and five point five | Forty thousand point five six | 10.00  |
| three | 公路自行车 | Ten thousand point two | Twenty-one thousand point five six | -3.59  |
| four | 公路自行车 | Fifteen thousand two hundred point five | Eighteen thousand | -0.50 |
| five | 赛车 | Thirty thousand five hundred point five | Forty-five thousand |  3.00 |

现在，我们将找到 Service_grade 列中所有记录的以 e 为基数的对数值。

```sql
Select Product_id, Product_name, Buying_price,  
Selling_price, Service_grade,
LN(Service_grade) AS GRADELOGN  
FROM Product;

```

**输出:**

| 产品标识 | 产品名称 | BUYING_PRICE | 销售价格 | 服务等级 | GRADELOGN |
| --- | --- | --- | --- | --- | --- |
| one | 旅游自行车 | Twenty thousand | Thirty thousand and fifty | 4.17  | 1.4279160358107101 |
| Two | 山地车 | Thirty thousand and five point five | Forty thousand point five six | 10.00  | 2.302585092994046 |
| three | 公路自行车 | Ten thousand point two | Twenty-one thousand point five six | -3.59  | 空 |
| four | 公路自行车 | Fifteen thousand two hundred point five | Eighteen thousand | -0.50 | 空 |
| five | 赛车 | Thirty thousand five hundred point five | Forty-five thousand |  3.00 | 1.0986122886681098 |