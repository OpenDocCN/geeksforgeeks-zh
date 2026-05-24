# MySQL 中的 MONTHNAME() 函数

> 原文: [https://www.geeksforgeeks.org/monthname-function-in-mysql/](https://www.geeksforgeeks.org/monthname-function-in-mysql/)

`MONTHNAME()` 函数用于从给定日期中查找月份名称。当日期的月份部分为 0 或大于 12 时，返回 0，否则返回 1 月到 12 月之间的月份名称。

## 语法

```sql
MONTHNAME(date)
```

## 参数

该方法接受一个参数：

*   `date`: 我们想要从中提取月份名称的日期或日期时间。

## 返回

返回给定日期的月份名称。

## 示例-1

使用 `MONTHNAME()` 函数查找当前月份名称。

```sql
SELECT MONTHNAME(NOW()) AS Current_Month;
```

**输出:**

| Current_Month |
| --- |
| November |

## 示例-2

使用 `MONTHNAME()` 函数从给定的日期时间中查找月份名称。

```sql
SELECT MONTHNAME('2015-01-26 08:09:22') AS MONTHNAME;
```

**输出:**

| MONTHNAME |
| --- |
| January |

## 示例-3

当日期为 `NULL` 时，使用 `MONTHNAME()` 函数。

```sql
SELECT MONTHNAME(NULL) AS MONTHNAME;
```

**输出:**

| MONTHNAME |
| --- |
| NULL |

## 示例-4

`MONTHNAME()` 函数也可以用来查找每个月售出的产品总数。首先，创建一个名为 `Product` 的表。

```sql
CREATE TABLE Product (
    Product_id INT AUTO_INCREMENT PRIMARY KEY,
    Product_name VARCHAR(255),
    Buying_price DECIMAL(10, 2),
    Selling_price DECIMAL(10, 2),
    Selling_Date DATE
);
```

现在在 `Product` 表中插入一些数据：

```sql
INSERT INTO
  Product(Product_name, Buying_price, Selling_price, Selling_Date)
VALUES
  ('Audi Q8', 10000000.00, 15000000.00, '2018-01-26' ),
  ('Volvo XC40', 2000000.00, 3000000.00, '2018-04-20' ),
  ('Audi A6', 4000000.00, 5000000.00, '2018-07-25' ),
  ('BMW X5', 5000500.00, 7006500.00, '2018-10-18'  ),
  ('Jaguar XF', 5000000, 7507000.00, '2019-01-27'  ),
  ('Mercedes-Benz C-Class', 4000000.00, 6000000.00, '2019-04-01'  ),
  ('Jaguar F-PACE', 5000000.00, 7000000.00, '2019-12-26'  ),
  ('Porsche Macan', 6500000.00, 8000000.00, '2020-04-16' ) ;
```

所以，我们的表看起来像：

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
|          6 | Mercedes-Benz C-Class |   4000000.00 |    6000000.00 | 2019-04-01   |
|          7 | Jaguar F-PACE         |   5000000.00 |    7000000.00 | 2019-12-26   |
|          8 | Porsche Macan         |   6500000.00 |    8000000.00 | 2020-04-16   |
+------------+-----------------------+--------------+---------------+--------------+
```

现在，我们将使用 `MONTHNAME()` 函数来查找每月销售的产品数量。

```sql
SELECT MONTHNAME(Selling_Date) MonthName,
COUNT(Product_id) Product_Sold
FROM Product
GROUP BY MONTHNAME(Selling_Date)
ORDER BY MONTHNAME(Selling_Date);
```

**输出:**

```sql
+-----------+--------------+
| MonthName | Product_Sold |
+-----------+--------------+
| April     |            3 |
| December  |            1 |
| January   |            2 |
| July      |            1 |
| October   |            1 |
+-----------+--------------+
```