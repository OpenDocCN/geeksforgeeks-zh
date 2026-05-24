# MySQL 中的 ROUND()函数

> 原文:[https://www.geeksforgeeks.org/round-function-in-mysql/](https://www.geeksforgeeks.org/round-function-in-mysql/)

MySQL 中的 **ROUND** ()函数用于将一个数字舍入到指定的小数位数。如果没有为舍入提供指定的小数位数，则舍入到最接近的整数。

**语法:**

```sql
ROUND(X, D)
```

**参数:**该方法在语法中接受两个参数，如上所述，如下所述–

*   **X :** 要四舍五入的数字。
*   **D :** 给定数字要四舍五入到的小数位数。它是可选的。如果没有给定，则将数字四舍五入到最接近的整数。如果是负数，则该数字四舍五入到小数点左边。

**返回:**返回四舍五入到指定位置后的数字。

**示例-1 :**
在未指定 D 的情况下舍入数字。

*   Rounding a Negative number.

    ```sql
    SELECT ROUND(-10.11) AS Rounded_Number;
    ```

    **输出:**

    | 四舍五入 _ 数字 |
    | --- |
    | -10 |

*   Rounding a Positive number.

    ```sql
    SELECT ROUND(100.61) AS Rounded_Number;
    ```

    **输出:**

    | 四舍五入 _ 数字 |
    | --- |
    | One hundred and one |

**例-2 :**
当 D 为负(-ve)时四舍五入。

*   Rounding a Negative number.

    ```sql
    SELECT ROUND(-1567.1100, -3) AS Rounded_Number;
    ```

    **输出:**

    | 四舍五入 _ 数字 |
    | --- |
    | -2000 |

*   Rounding a Positive number.

    ```sql
    SELECT ROUND(1016.6089, -1) AS Rounded_Number;
    ```

    **输出:**

    | 四舍五入 _ 数字 |
    | --- |
    | One thousand and twenty |

**示例-3 :**
当 D 为正(+ve)时，四舍五入一个数字。

*   Rounding a Negative number up to 2 decimal places.

    ```sql
    SELECT ROUND(-1567.1160, 2) AS Rounded_Number;
    ```

    **输出:**

    | 四舍五入 _ 数字 |
    | --- |
    | -1567.12 |

*   Rounding a Positive number up to three decimal places.

    ```sql
    SELECT ROUND(1016.6019, 3) AS Rounded_Number;
    ```

    **输出:**

    | 四舍五入 _ 数字 |
    | --- |
    | One thousand and sixteen point six zero two |

**示例-4 :**
ROUND 函数也可用于查找列数据的舍入值。在本例中，我们将查找价格列的舍入值。为了演示，创建一个名为**产品的表格。**

```sql
CREATE TABLE Product(
    Product_id INT AUTO_INCREMENT, 
    Product_name VARCHAR(100) NOT NULL,
    Buying_price DECIMAL(13, 6) NOT NULL,
    Selling_price DECIMAL(13, 6) NOT NULL,
    Selling_Date Date NOT NULL,
    PRIMARY KEY(Product_id)
);
```

现在在产品表中插入一些数据–

```sql
INSERT INTO 
    Product(Product_name, Buying_price, Selling_price, Selling_Date)
VALUES
    ('P6', 1060.865460, 1700.675400, '2020-08-26'),
    ('P2', 2000.154300, 3050.986700, '2020-08-27'),
    ('P1', 4000.874300, 5070.786500, '2020-08-28'),
    ('P2', 2090.654300, 3050.896500, '2020-09-01'),
    ('P3', 5900.543280, 7010.654700, '2020-09-04'),
    ('P4', 4000.353200, 4500.125400, '2020-09-05'),
    ('P5', 5010.768900, 6000.873200, '2020-09-08');
```

因此，产品表是–

| 产品 id | 产品名称 | 购买价格 | 销售价格 | 销售日期 |
| --- | --- | --- | --- | --- |
| one | P6 | 1060.865460 | 1700.675400 | 2020-08-26 |
| Two | P2 | 2000.154300 | 3050.986700 | 2020-08-27 |
| three | 第一亲代 | 4000.874300 | 5070.786500 | 2020-08-28 |
| four | P2 | 2090.654300 | 3050.896500 | 2020-09-01 |
| five | P3 | 4000.353200 | 7010.654700 | 2020-09-04 |
| six | P4 | 4000.353200 | 4500.125400 | 2020-09-05 |
| seven | 孕烯醇酮 | 5010.768900 | 6000.873200 | 2020-09-08 |

现在，我们将买价和卖价列四舍五入到小数点后两位。

```sql
SELECT Product_name, Buying_price, ROUND(Buying_price, 2) Rounded_Bprice, 
Selling_price, ROUND(Selling_price, 2) Rounded_Sprice
FROM Product;
```

**输出:**

| 产品名称 | 购买价格 | 圆形 _Bprice | 销售价格 | 圆形 _Sprice |
| --- | --- | --- | --- | --- |
| P6 | 1060.865460 | One thousand and sixty point eight seven | 1700.675400 | One thousand seven hundred point six eight |
| P2 | 2000.154300 | Two thousand point one five | 3050.986700 | Three thousand and fifty point nine nine |
| 第一亲代 | 4000.874300 | Four thousand point eight seven | 5070.786500 | Five thousand and seventy point seven nine |
| P2 | 2090.654300 | Two thousand and ninety point six five | 3050.896500 | Three thousand and fifty point nine |
| P3 | 5900.543280 | Five thousand nine hundred point five four | 7010.654700 | Seven thousand and ten point six five |
| P4 | 4000.353200 | Four thousand point three five | 4500.125400 | Four thousand five hundred point one three |
| 孕烯醇酮 | 5010.768900 | Five thousand and ten point seven seven | 6000.873200 | Six thousand point eight seven |