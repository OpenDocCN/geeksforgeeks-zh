# MySQL 中的 QUARTER()函数

> 原文: [https://www.geeksforgeeks.org/quarter-function-in-mysql/](https://www.geeksforgeeks.org/quarter-function-in-mysql/)

[MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中的 `QUARTER()` 函数用于返回给定日期值的季度。它返回一个从 1 到 4 的数字。

## 语法

```sql
QUARTER(date)
```

## 参数

函数只接受一个参数

*   `Date`: 我们想要提取其季度的日期或日期时间值。

## 返回

如果给定日期在 1-3 月范围内，则返回 1。4 月-6 月为 2，7 月-9 月为 3，如果日期在 10 月-12 月的范围内，则返回 4。

## 示例-1

使用 `QUARTER()` 函数查找当前季度。

```sql
SELECT QUARTER(NOW()) AS CURRENT_QUARTER;
```

**输出:**

| CURRENT_QUARTER |
| --- |
| 4 |

## 示例-2

使用 `QUARTER()` 函数从给定的日期时间中查找季度。

```sql
SELECT QUARTER('2020-04-26 08:09:22') AS QUARTER_NUMBER;
```

**输出:**

| QUARTER_NUMBER |
| --- |
| 2 |

## 示例-3

当日期为 `NULL` 时，使用 `QUARTER()` 函数从给定的日期时间中查找季度。

```sql
SELECT QUARTER(NULL) AS QUARTER_NUMBER;
```

**输出:**

| QUARTER_NUMBER |
| --- |
| NULL |

## 示例-4

`QUARTER()` 函数也可用于查找每个季度的总销售额。演示创建一个名为 `Product` 的表。

现在在 `Product` 表中插入一些数据:

```sql
INSERT INTO  
  Product(Product_name, Buying_price, Selling_price, Selling_Date)
VALUES
  ('Audi Q8', 10000000.00, 15000000.00, '2018-01-26' ),
  ('Volvo XC40', 2000000.00, 3000000.00, '2018-04-20' ),
  ('Audi A6', 4000000.00, 5000000.00, '2018-07-25' ),
  ('BMW X5', 5000500.00, 7006500.00, '2018-10-18'  ),
  ('Jaguar XF', 5000000, 7507000.00, '2018-01-27'  ),
  ('Mercedes-Benz C-Class', 4000000.00, 6000000.00, '2018-04-01'  ),
  ('Jaguar F-PACE', 5000000.00, 7000000.00, '2018-12-26'  ),
  ('Porsche Macan', 6500000.00, 8000000.00, '2018-04-16' ) ;
```

所以，我们的表看起来像:

| Product_id | Product_name | Purchase_price | Sales_price | Sales_date |
| --- | --- | --- | --- | --- |
| 1 | Audi Q8 | 10000000.00 | 15000000.00 | 2018-01-26 |
| 2 | Volvo XC40 | 2000000.00 | 3000000.00 | 2018-04-20 |
| 3 | Audi A6 | 4000000.00 | 5000000.00 | 2018-07-25 |
| 4 | BMW X5 | 5000500.00 | 7006500.00 | 2018-10-18 |
| 5 | Jaguar XF | 5000000.00 | 7507000.00 | 2018-01-27 |
| 6 | Mercedes-Benz C-Class | 4000000.00 | 6000000.00 | 2018-04-01 |
| 7 | Jaguar F-PACE | 5000000.00 | 7000000.00 | 2018-12-26 |
| 8 | Porsche Macan | 6500000.00 | 8000000.00 | 2018-04-16 |

现在，我们将使用 `MONTH()` 函数来查找每个季度销售的产品数量。

```sql
SELECT 
    QUARTER(Selling_Date) as quarter, 
    COUNT(Product_id) as PRODUCT_SOLD 
FROM 
    Product   
GROUP BY QUARTER(Selling_Date)       
ORDER BY QUARTER(Selling_Date);
```

**输出:**

| quarter | PRODUCT_SOLD |
| --- | --- |
| 1 | 2 |
| 2 | 3 |
| 3 | 1 |
| 4 | 2 |