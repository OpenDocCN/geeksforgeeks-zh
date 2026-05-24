# MySQL 中的 SYSDATE()函数

> 原文:[https://www.geeksforgeeks.org/sysdate-function-in-mysql/](https://www.geeksforgeeks.org/sysdate-function-in-mysql/)

**MySQL 中的 SYSDATE** ()函数用于根据函数的上下文，以 YYYY-MM-DD HH:MM:SS 或 YYYYMMDDHHMMSS.uuuuuu 格式返回当前日期和时间。

**语法:**

```sql
SYSDATE()

```

**参数:**
此方法不接受任何参数。

**返回:**
返回当前日期时间值。

**示例-1 :**
使用 SYSDATE 函数获取当前日期和时间。

```sql
SELECT SYSDATE() as CurrentDateAndTime ;

```

**输出:**

| 当前日期和时间 |
| --- |
| 2020-11-26 01:31:14 |

**示例-2 :**
使用数字格式的 SYSDATE 函数获取当前日期和时间。

```sql
SELECT SYSDATE() + 0 as CurrDateAndTime ;

```

**输出:**

| CURRDATEANDTIME |
| --- |
| 20201126013648 |

**示例-3 :**
可以使用 SYSDATE 函数设置列的值。为了演示，创建一个名为 DeliveryDetails 的表。

```sql
CREATE TABLE DeliveryDetails (
DeliveryId INT AUTO_INCREMENT,
ProductId INT NOT NULL,
ProductName VARCHAR(20) NOT NULL,
Delivered_At TIMESTAMP NOT NULL,
PRIMARY KEY(DeliveryId)
);

```

在这里，我们将使用 SYSDATE 函数，当一个交付将被完成。“交货时间”列中的值将是系统日期函数给出的值。

```sql
INSERT INTO  
DeliveryDetails(ProductId, ProductName, Delivered_At)
VALUES
(94567, 'Acer Helios', SYSDATE());
```

现在，检查交货详细信息表:

```sql
SELECT * FROM DeliveryDetails;

```

**输出:**

| DeliveryId | 产品 id | 产品名称 | 交货时间 |
| --- | --- | --- | --- |
| one | Ninety-four thousand five hundred and sixty-seven | 赫利俄斯钢铁 | 2020-11-26 01:40:57 |