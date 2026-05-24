# MySQL 中的 MONTH() 函数

> 原文: [https://www.geeksforgeeks.org/month-function-in-mysql/](https://www.geeksforgeeks.org/month-function-in-mysql/)

`MONTH()` 函数在 [MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中用来查找给定日期的月份。当日期的月份部分为 0 时，它返回 0，否则它返回 1 到 12 之间的月份值。

## 语法

```sql
MONTH(date)
```

## 参数

该函数接受一个参数：

*   `date`: 我们要从中提取月份的日期或日期时间。

## 返回值

返回 1 到 12 之间的值。

## 示例-1

使用 `MONTH()` 函数查找当前月份。

```sql
SELECT MONTH(NOW()) AS Current_Month;
```

**输出:**

| CURRENT_MONTH |
| --- |
| 11 |

## 示例-2

使用 `MONTH()` 函数从给定的日期时间中查找月份。

```sql
SELECT MONTH('2015-09-26 08:09:22') AS MONTH;
```

**输出:**

| MONTH |
| --- |
| 9 |

## 示例-3

当日期为 `NULL` 时，使用 `MONTH()` 函数从给定的日期时间中查找月份。

```sql
SELECT MONTH(NULL) AS Month ;
```

**输出:**

| Month |
| --- |
| NULL |

## 示例-4

`MONTH` 函数也可以用来查找每个月销售的产品总数。演示创建一个名为 `Product` 的表。

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

| Product_id | Product_name | Buying_price | Selling_price | Selling_Date |
| --- | --- | --- | --- | --- |
| 1 | Audi Q8 | 10000000.00 | 15000000.00 | 2018-01-26 |
| 2 | Volvo XC40 | 2000000.00 | 3000000.00 | 2018-04-20 |
| 3 | Audi A6 | 4000000.00 | 5000000.00 | 2018-07-25 |
| 4 | BMW X5 | 5000500.00 | 7006500.00 | 2018-10-18 |
| 5 | Jaguar XF | 5000000.00 | 7507000.00 | 2019-01-27 |
| 6 | Mercedes-Benz C-Class | 4000000.00 | 6000000.00 | 2019-04-01 |
| 7 | Jaguar F-PACE | 5000000.00 | 7000000.00 | 2019-12-26 |
| 8 | Porsche Macan | 6500000.00 | 8000000.00 | 2020-04-16 |

现在，我们将使用 `MONTH()` 函数来查找每月销售的产品数量。

```sql
SELECT  
   MONTH(Selling_Date) month,  
   COUNT(Product_id) Product_Sold
FROM Product
GROUP BY MONTH(Selling_Date)
ORDER BY MONTH(Selling_Date);
```

**输出:**

| month | Product_Sold |
| --- | --- |
| 1 | 2 |
| 4 | 2 |
| 7 | 1 |
| 10 | 1 |
| 12 | 1 |