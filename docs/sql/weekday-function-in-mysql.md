# MySQL 中的 WEEKDAY()函数

> 原文:[https://www.geeksforgeeks.org/weekday-function-in-mysql/](https://www.geeksforgeeks.org/weekday-function-in-mysql/)

**WEEKDAY** ()函数在 MySQL 中用于查找给定日期的 WEEKDAY 值。如果日期为空，WEEKDAY()函数将返回空值。否则，它将返回某个日期的索引，即 0 代表星期一，1 代表星期二，6 代表星期日。

**语法:**

```sql
WEEKDAY(date)

```

**参数:**该方法接受一个参数，如上所述，如下所述:

*   **Date:** The date or date time from which we want to extract the working day value.

**返回:**返回给定日期的工作日值。

**例-1:**2020 年 9 月 27 日使用 weekday()函数求当前日期的 WEEKDAY 值。

```sql
SELECT WEEKDAY(NOW()) AS  WeekDay;

```

**输出:**

```sql
mysql> SELECT WEEKDAY(NOW()) AS WeekDay;
+---------+
| WeekDay |
+---------+
|       6 |
+---------+

```

因此，当 WEEKDAY 函数返回 6 时，当前日期是“星期日”。

**示例-2 :** 使用 weekday()函数从给定的日期时间中查找工作日值。

```sql
SELECT WEEKDAY ('2017-08-22 08:09:22') AS WeekDay_Value ;

```

**输出:**

```sql
+---------------+
| WeekDay_Value |
+---------------+
|             1 |
+---------------+

```

因此，在本例中，日期是“星期二”。

**示例-3 :** 当日期为空时，使用 weekday()函数从给定的日期时间中查找工作日值。

```sql
SELECT WEEKDAY (NULL) AS WeekDay_Value ;

```

**输出:**

```sql
+---------------+
| WeekDay_Value |
+---------------+
|          NULL |
+---------------+

```

**示例-4 :** 在本例中，我们将查找每个工作日售出的产品数量。演示创建一个名为。

**产品:**T0】

现在在产品表中插入一些数据:

```sql
INSERT INTO 
    Product(Product_name, Buying_price, Selling_price, Selling_Date)
VALUES
    ('Audi Q8', 10000000.00, 15000000.00, '2020-08-26' ),
    ('Volvo XC40', 2000000.00, 3000000.00, '2020-08-27' ),
    ('Audi A6', 4000000.00, 5000000.00, '2020-08-28' ),
    ('BMW X5', 5000500.00, 7006500.00, '2020-09-01'  ),
    ('Jaguar XF', 5000000, 7507000.00, '2020-09-04'  ),
        ('Mercedes-Benz C-Class', 4000000.00, 6000000.00, '2020-09-05'  ),
        ('Jaguar F-PACE', 5000000.00, 7000000.00, '2020-09-08'  ),
        ('Volvo S90', 4500000.00, 6000000.00, '2020-09-11'  ),
        ('BMW X4', 4000000.00, 6200000.00, '2020-09-12'  ),
    ('Porsche Macan', 6500000.00, 8000000.00, '2020-09-16' ) ;

```

因此，产品表为:

```sql
mysql> Select * from Product;
+------------+-----------------------+--------------+---------------+--------------+
| Product_id | Product_name          | Buying_price | Selling_price | Selling_Date |
+------------+-----------------------+--------------+---------------+--------------+
|          1 | Audi Q8               |  10000000.00 |   15000000.00 | 2020-08-26   |
|          2 | Volvo XC40            |   2000000.00 |    3000000.00 | 2020-08-27   |
|          3 | Audi A6               |   4000000.00 |    5000000.00 | 2020-08-28   |
|          4 | BMW X5                |   5000500.00 |    7006500.00 | 2020-09-01   |
|          5 | Jaguar XF             |   5000000.00 |    7507000.00 | 2020-09-04   |
|          6 | Mercedes-Benz C-Class |   4000000.00 |    6000000.00 | 2020-09-05   |
|          7 | Jaguar F-PACE         |   5000000.00 |    7000000.00 | 2020-09-08   |
|          8 | Volvo S90             |   4500000.00 |    6000000.00 | 2020-09-11   |
|          9 | BMW X4                |   4000000.00 |    6200000.00 | 2020-09-12   |
|         10 | Porsche Macan         |   6500000.00 |    8000000.00 | 2020-09-16   |
+------------+-----------------------+--------------+---------------+--------------+

```

现在，我们将找到每个工作日售出的产品数量。

```sql
SELECT 
    WEEKDAY (Selling_Date) WeekDay, 
    COUNT(Product_id) Product_Sold
FROM 
    Product
GROUP BY WEEKDAY(Selling_Date)
ORDER BY WEEKDAY(Selling_Date);

```

**输出:**

```sql
+---------+--------------+
| WeekDay | Product_Sold |
+---------+--------------+
|       1 |            2 |
|       2 |            2 |
|       3 |            1 |
|       4 |            3 |
|       5 |            2 |
+---------+--------------+

```