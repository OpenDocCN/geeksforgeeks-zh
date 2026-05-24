# MySQL 中的 LOG()函数

> 原文:[https://www.geeksforgeeks.org/log-function-in-mysql/](https://www.geeksforgeeks.org/log-function-in-mysql/)

**LOG** ()函数在 MySQL 中用于计算特定数字的自然对数。数字必须是> 0，否则返回空值。

**语法:**

```sql
LOG(X)

```

**参数:**这个方法接受一个参数，如上所述，如下所述:

*   **X:** A number whose logarithmic value we want to calculate. It should be positive.

**返回:**返回给定数字 x 的自然对数。

**示例-1 :** 使用 LOG()函数对给定数字进行对数运算。

```sql
SELECT LOG(5) AS Log_Val ;

```

**输出:**

| 【日志 _ 下降】 |
| --- |
| 【1.6094379124341003】 |

**示例-2 :** 使用 LOG()函数对 0 求对数。

```sql
SELECT LOG(0) AS Log_Val ;

```

**输出:**

| 【日志 _ 下降】 |
| --- |
| 【无效】 |

**例-3:**LOG 函数也可以用来求一列数据列的对数值。演示创建一个名为。

**产品:**T0】

现在在产品表中插入一些数据:

```sql
INSERT INTO 
    Product(Product_name, Buying_price, Selling_price, Service_grade)
VALUES
    ('Touring Bike', 2019.00, 3009.6, 0.89 ),
    ('Mountain Bike', 3019.50, 4000.56, 1.00 ),
    ('Road Bike', 1019.20, 2000.56, -0.89 ),
    ('Road Bicycle', 1019.50, 1500.56, -1.50 ),
    ('Racing Bicycle', 3019.50, 4000.56, 2.00) ;

```

所以，我们的桌子看起来像:

```sql
mysql> Select * from Product;
+------------+----------------+--------------+---------------+---------------+
| Product_id | Product_name   | Buying_price | Selling_price | Service_grade |
+------------+----------------+--------------+---------------+---------------+
|          1 | Touring Bike   |      2019.00 |       3009.60 |          0.89 |
|          2 | Mountain Bike  |      3019.50 |       4000.56 |          1.00 |
|          3 | Road Bike      |      1019.20 |       2000.56 |         -0.89 |
|          4 | Road Bicycle   |      1019.50 |       1500.56 |         -1.50 |
|          5 | Racing Bicycle |      3019.50 |       4000.56 |          2.00 |
+------------+----------------+--------------+---------------+---------------+
5 rows in set (0.00 sec)

```

现在，我们将找到 Service_grade 列中所有记录的对数值。

```sql
Select Product_id,  
 Product_name,  
 Buying_price,  
 Selling_price,  
 Service_grade,
 LOG(Service_grade) AS GRADELOG  
 FROM Product;

```

**输出:**

```sql
+------------+----------------+--------------+---------------+---------------+----------------------+
| Product_id | Product_name   | Buying_price | Selling_price | Service_grade | GRADELOG             |
+------------+----------------+--------------+---------------+---------------+----------------------+
|          1 | Touring Bike   |      2019.00 |       3009.60 |          0.89 | -0.11653381625595151 |
|          2 | Mountain Bike  |      3019.50 |       4000.56 |          1.00 |                    0 |
|          3 | Road Bike      |      1019.20 |       2000.56 |         -0.89 |                 NULL |
|          4 | Road Bicycle   |      1019.50 |       1500.56 |         -1.50 |                 NULL |
|          5 | Racing Bicycle |      3019.50 |       4000.56 |          2.00 |   0.6931471805599453 |
+------------+----------------+--------------+---------------+---------------+----------------------+
```