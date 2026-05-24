# MySQL 中的 YEAR()函数

> 原文:[https://www.geeksforgeeks.org/year-function-in-mysql/](https://www.geeksforgeeks.org/year-function-in-mysql/)

**YEAR** ()函数在 MySQL 中用来查找给定日期开始的年份。如果日期为空，YEAR()函数将返回空值。否则，它将返回 1000 到 9999 之间的值。

**语法:**

```sql
YEAR(date)  

```

**参数:**该方法接受一个参数，如上所述，如下所述:

*   **Date:** The date or date time from which we want to extract the year.

**返回:**返回 1000 到 9999 之间的值。

**示例-1 :** 使用 Year()函数查找当前年份。

```sql
SELECT YEAR(NOW()) AS Current_Year;

```

**输出:**

```sql
mysql> SELECT YEAR(NOW()) AS Current_Year;
+--------------+
| Current_Year |
+--------------+
|         2020 |
+--------------+
1 row in set (0.00 sec)

```

**示例-2 :** 使用 Year()函数从给定的日期时间中查找年份。

```sql
SELECT YEAR('2015-09-26 08:09:22') AS Year ;

```

**输出:**

```sql
+------+
| Year |
+------+
| 2015 |
+------+

```

**示例-3 :** 当日期为空时，使用 Year()函数从给定的日期时间中查找年份。

```sql
SELECT YEAR(NULL) AS Year ;

```

**输出:**

```sql
+------+
| Year |
+------+
| NULL |
+------+

```

**示例-4:**YEAR 函数也可以用来查找一年中售出的产品总数。演示创建一个名为。

**产品:**T0】

现在在产品表中插入一些数据:

```sql
INSERT INTO 
    Product(Product_name, Buying_price, Selling_price, Selling_Date)
VALUES
    ('Audi Q8', 10000000.00, 15000000.00, '2018-01-26' ),
    ('Volvo XC40', 2000000.00, 3000000.00, '2018-04-20' ),
    ('Audi A6', 4000000.00, 5000000.00, '2018-07-25' ),
    ('BMW X5', 5000500.00, 7006500.00, '2018-10-18'  ),
    ('Jaguar XF', 5000000, 7507000.00, '2019-01-27'  ),
        ('Mercedes-Benz C-Class', 4000000.00, 6000000.00, '2019-09-01'  ),
        ('Jaguar F-PACE', 5000000.00, 7000000.00, '2019-12-26'  ),
    ('Porsche Macan', 6500000.00, 8000000.00, '2020-06-16' ) ;

```

所以，我们的桌子看起来像:

```sql
mysql> SELECT * FROM Product;
+------------+-----------------------+--------------+---------------+--------------+
| Product_id | Product_name          | Buying_price | Selling_price | Selling_Date |
+------------+-----------------------+--------------+---------------+--------------+
|          1 | Audi Q8               |  10000000.00 |   15000000.00 | 2018-01-26   |
|          2 | Volvo XC40            |   2000000.00 |    3000000.00 | 2018-04-20   |
|          3 | Audi A6               |   4000000.00 |    5000000.00 | 2018-07-25   |
|          4 | BMW X5                |   5000500.00 |    7006500.00 | 2018-10-18   |
|          5 | Jaguar XF             |   5000000.00 |    7507000.00 | 2019-01-27   |
|          6 | Mercedes-Benz C-Class |   4000000.00 |    6000000.00 | 2019-09-01   |
|          7 | Jaguar F-PACE         |   5000000.00 |    7000000.00 | 2019-12-26   |
|          8 | Porsche Macan         |   6500000.00 |    8000000.00 | 2020-06-16   |
+------------+-----------------------+--------------+---------------+--------------+

```

现在，我们将使用 year()函数来查找每年销售的产品数量。

```sql
SELECT 
    YEAR(Selling_Date) year, 
    COUNT(Product_id) Product_Sold
FROM 
    Product
GROUP BY YEAR(Selling_Date)
ORDER BY YEAR(Selling_Date);

```

**输出:**

```sql
+------+--------------+
| year | Product_Sold |
+------+--------------+
| 2018 |            4 |
| 2019 |            3 |
| 2020 |            1 |
+------+--------------+

```