# MySQL 中的 QUARTER()函数

> 原文:[https://www.geeksforgeeks.org/quarter-function-in-mysql/](https://www.geeksforgeeks.org/quarter-function-in-mysql/)

[MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中的 **QUARTER** ()函数用于返回给定日期值的季度。它返回一个从 1 到 4 的数字。

**语法:**

```sql
QUARTER(date)
```

**参数:**函数只接受一个参数

*   **Date** : We want to extract the date or date time of the quarter.

**返回**:如果给定日期在 1-3 月范围内，则返回 1。4 月-6 月为 2，7 月-9 月为 3，如果日期在 10 月-12 月的范围内，则返回 4。

**示例-1 :**

使用季度()函数查找当前季度。

```sql
SELECT QUARTER(NOW()) AS CURRENT_QUARTER;
```

**输出:**T5】

| CURRENT _ QUARTER |
| --- |
| 4 |

**示例-2 :**

使用 Quarter()函数从给定的日期时间中查找季度。

```sql
SELECT QUARTER('2020-04-26 08:09:22') AS QUARTER_NUMBER;
```

**输出:**T5】

|  |
| --- |
| 2 |

**示例-3 :**

当日期为空时，使用 Quarter()函数从给定的日期时间中查找季度。

```sql
SELECT QUARTER(NULL) AS QUARTER_NUMBER;
```

**输出:**T5】

|  |
| --- |
| 空 |

**示例-4 :**

季函数也可用于查找每个季度的总销售额。演示创建一个名为。

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
  ('Jaguar XF', 5000000, 7507000.00, '2018-01-27'  ),
  ('Mercedes-Benz C-Class', 4000000.00, 6000000.00, '2018-04-01'  ),
  ('Jaguar F-PACE', 5000000.00, 7000000.00, '2018-12-26'  ),
  ('Porsche Macan', 6500000.00, 8000000.00, '2018-04-16' ) ;
```

所以，我们的表看起来像:T22】2018-01-26T68】7507000.00T70】2019-01-27T72T74】6T76】奔驰 C 级 T78】4000000.00T80】600000.00【T81

| Product _id | Product _ name | Purchase _ price | Sales _ price | Sales _ date; |
| --- | --- | --- | --- | --- |
| one | Audi Q8 | One million | Fifteen million |
| Two | Volvo XC40 | Two hundred thousand | Three hundred thousand | Five million |

现在，我们将使用 **MONTH ()** 功能来查找每个季度销售的产品数量。

```sql
SELECT 
    QUARTER(Selling_Date) as quarter, 
    COUNT(Product_id) as PRODUCT_SOLD 
FROM 
    Product   
GROUP BY QUARTER(Selling_Date)       
ORDER BY QUARTER(Selling_Date);
```

**输出:**T15T18】3T21T27T30】2T32T34T35

| 四分之一 | 产品 _ seld |
| --- | --- |
| one | Two |
| Two | three | one | four |