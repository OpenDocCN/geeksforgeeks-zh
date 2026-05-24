# MySQL 中的 ROUND() 函数

> 原文: [https://www.geeksforgeeks.org/round-function-in-mysql/](https://www.geeksforgeeks.org/round-function-in-mysql/)

MySQL 中的 `ROUND()` 函数用于将一个数字舍入到指定的小数位数。如果没有为舍入提供指定的小数位数，则舍入到最接近的整数。

## 语法

```sql
ROUND(X, D)
```

## 参数

该方法在语法中接受两个参数，如上所述，如下所述：

*   `X`：要四舍五入的数字。
*   `D`：给定数字要四舍五入到的小数位数。它是可选的。如果没有给定，则将数字四舍五入到最接近的整数。如果是负数，则该数字舍入到小数点左边。

## 返回

返回四舍五入到指定位置后的数字。

## 示例-1

在未指定 `D` 的情况下舍入数字。

*   舍入一个负数。

```sql
SELECT ROUND(-10.11) AS Rounded_Number;
```

**输出：**

| Rounded_Number |
| --- |
| -10 |

*   舍入一个正数。

```sql
SELECT ROUND(100.61) AS Rounded_Number;
```

**输出：**

| Rounded_Number |
| --- |
| 101 |

## 示例-2

当 `D` 为负数时舍入。

*   舍入一个负数。

```sql
SELECT ROUND(-1567.1100, -3) AS Rounded_Number;
```

**输出：**

| Rounded_Number |
| --- |
| -2000 |

*   舍入一个正数。

```sql
SELECT ROUND(1016.6089, -1) AS Rounded_Number;
```

**输出：**

| Rounded_Number |
| --- |
| 1020 |

## 示例-3

当 `D` 为正数时，舍入一个数字。

*   将一个负数舍入到 2 位小数。

```sql
SELECT ROUND(-1567.1160, 2) AS Rounded_Number;
```

**输出：**

| Rounded_Number |
| --- |
| -1567.12 |

*   将一个正数舍入到 3 位小数。

```sql
SELECT ROUND(1016.6019, 3) AS Rounded_Number;
```

**输出：**

| Rounded_Number |
| --- |
| 1016.602 |

## 示例-4

`ROUND` 函数也可用于查找列数据的舍入值。在本例中，我们将查找 `price` 列的舍入值。为了演示，创建一个名为 `Product` 的表格。

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

现在在 `Product` 表中插入一些数据：

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

因此，`Product` 表是：

| Product_id | Product_name | Buying_price | Selling_price | Selling_Date |
| --- | --- | --- | --- | --- |
| 1 | P6 | 1060.865460 | 1700.675400 | 2020-08-26 |
| 2 | P2 | 2000.154300 | 3050.986700 | 2020-08-27 |
| 3 | P1 | 4000.874300 | 5070.786500 | 2020-08-28 |
| 4 | P2 | 2090.654300 | 3050.896500 | 2020-09-01 |
| 5 | P3 | 5900.543280 | 7010.654700 | 2020-09-04 |
| 6 | P4 | 4000.353200 | 4500.125400 | 2020-09-05 |
| 7 | P5 | 5010.768900 | 6000.873200 | 2020-09-08 |

现在，我们将 `Buying_price` 和 `Selling_price` 列舍入到小数点后两位。

```sql
SELECT Product_name, Buying_price, ROUND(Buying_price, 2) Rounded_Bprice, 
Selling_price, ROUND(Selling_price, 2) Rounded_Sprice
FROM Product;
```

**输出：**

| Product_name | Buying_price | Rounded_Bprice | Selling_price | Rounded_Sprice |
| --- | --- | --- | --- | --- |
| P6 | 1060.865460 | 1060.87 | 1700.675400 | 1700.68 |
| P2 | 2000.154300 | 2000.15 | 3050.986700 | 3050.99 |
| P1 | 4000.874300 | 4000.87 | 5070.786500 | 5070.79 |
| P2 | 2090.654300 | 2090.65 | 3050.896500 | 3050.90 |
| P3 | 5900.543280 | 5900.54 | 7010.654700 | 7010.65 |
| P4 | 4000.353200 | 4000.35 | 4500.125400 | 4500.13 |
| P5 | 5010.768900 | 5010.77 | 6000.873200 | 6000.87 |