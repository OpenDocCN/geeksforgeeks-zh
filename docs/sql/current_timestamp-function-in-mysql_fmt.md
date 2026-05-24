# MySQL 中的 CURRENT_TIMESTAMP() 函数

> 原文: [https://www.geeksforgeeks.org/current_timestamp-function-in-mysql/](https://www.geeksforgeeks.org/current_timestamp-function-in-mysql/)

MySQL 中的 `CURRENT_TIMESTAMP()` [函数](https://www.geeksforgeeks.org/sql-functions-aggregate-scalar-functions/)用于获取当前的日期和时间值。在 MySQL 函数中，当您需要记录确切的交付时间时，就需要 `CURRENT_TIMESTAMP`，这有助于改善任何组织的服务和功能。该函数返回格式为 `YYYY-MM-DD HH:MM:SS` 或 `YYYYMMDDHHMMSS.uuuuuu` 的当前日期和时间值，具体取决于该函数是在字符串还是数字上下文中使用。

让我们考虑一个例子，以更好地了解：如果你已经购买或使用过快递服务，那么你会看到他们会为你提供一个唯一的标识，以保持更新和跟踪你的产品位置。在快递的情况下，在购买的情况下，你会得到更新的确切位置、你的产品是什么时候发出的以及预期的日期等。你会得到所有信息。在这两种情况下，都需要 `CURRENT_TIMESTAMP` 来跟踪交货地点的当前时间。

## 语法

```sql
CURRENT_TIMESTAMP
OR
CURRENT_TIMESTAMP()
```

## 参数

此方法不接受任何参数。

## 返回

返回当前日期时间值。

## 示例-1

使用 `CURRENT_TIMESTAMP` 函数获取当前日期和时间。

```sql
SELECT CURRENT_TIMESTAMP 
as CurrDateAndTime ;
```

**输出:**

| CURRDATEANDTIME |
| --- |
| 2020-10-13 14:40:10 |

## 示例-2

使用 `CURRENT_TIMESTAMP` 函数获取数字格式的当前日期和时间。

```sql
SELECT CURRENT_TIMESTAMP + 0 
as CurrDateAndTime ;
```

**输出:**

| CURRDATEANDTIME |
| --- |
| 20201013144123 |

## 示例-3

`CURRENT_TIMESTAMP` 函数可以用来设置列的值。为了演示，创建一个名为 `Details_of_Delivery` 的表。

```sql
CREATE TABLE Details_of_Delivery (
Delivery_Id INT AUTO_INCREMENT,
Product_Id INT NOT NULL,
Product_Name VARCHAR(20) NOT NULL,
Delivered_At_time TIMESTAMP NOT NULL,
PRIMARY KEY(Delivery_Id)
);
```

在这里，我们将使用 `CURRENT_TIMESTAMP` 函数来完成交付。“交付时间”列中的值将是当前时间戳函数给出的值。

```sql
INSERT INTO  
Details_of_Delivery(Product_Id, Product_Name, Delivered_At_time)
VALUES
(990067, 'Acer Nitro', CURRENT_TIMESTAMP );
INSERT INTO  
Details_of_Delivery(Product_Id, Product_Name, Delivered_At_time)
VALUES
(990068, 'Dell', CURRENT_TIMESTAMP );
```

现在，检查交货明细表。

```sql
SELECT * FROM Details_of_Delivery;
```

**输出:**

| 交货标识 | 产品标识 | 产品名称 | 交货时间 |
| --- | --- | --- | --- |
| 1 | 990067 | Acer Nitro | 2020-10-13 14:43:48 |
| 2 | 990068 | Dell | 2020-10-13 14:45:48 |