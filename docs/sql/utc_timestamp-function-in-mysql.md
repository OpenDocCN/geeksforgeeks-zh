# MySQL 中的 UTC_TIMESTAMP()函数

> 原文:[https://www . geesforgeks . org/utc _ timestamp-function-in-MySQL/](https://www.geeksforgeeks.org/utc_timestamp-function-in-mysql/)

**UTC _ TIMESTAMP**()MySQL 中的函数用于检查当前协调世界时(UTC)的日期和时间值。它以 YYYY-MM-DD HH:MM:SS 或 YYYYMMDDHHMMSS.uuu 格式返回当前 UTC 日期和时间值，具体取决于该函数是在字符串还是数字上下文中使用。

**语法:**

```sql
UTC_TIMESTAMP
 OR
UTC_TIMESTAMP()

```

**参数:**
此方法不接受任何参数。

**返回:**
返回当前 UTC 日期时间值。

**示例-1 :**
使用 UTC_TIMESTAMP 函数获取当前 UTC 日期和时间。

```sql
SELECT UTC_TIMESTAMP as CurrUtcDateAndTime ;

```

**输出:**

| 当前日期和时间 |
| --- |
| 2020-10-09 18:08:13 |

**示例-2 :**
使用 UTC_TIMESTAMP 函数以数字格式获取当前 UTC 日期和时间。

```sql
SELECT UTC_TIMESTAMP + 0 as CurrUtcDateAndTime ;

```

**输出:**

| 当前日期和时间 |
| --- |
| 20201009180940 |

**示例-3 :**
可以使用 UTC_TIMESTAMP 函数设置列的值。为了演示，创建一个名为 DeliveryDetails 的表。

```sql
CREATE TABLE DeliveryDetails (
DeliveryId INT AUTO_INCREMENT,
ProductId INT NOT NULL,
ProductName VARCHAR(20) NOT NULL,
Delivered_At TIMESTAMP NOT NULL,
PRIMARY KEY(DeliveryId)
);

```

在这里，我们将使用 UTC_TIMESTAMP 函数来完成交付。“交付时间”列中的值将是世界协调时时间戳函数给出的值。

```sql
INSERT INTO  
DeliveryDetails(ProductId, ProductName, Delivered_At)
VALUES
(1010001, 'Dell  Inspirion', UTC_TIMESTAMP );

```

现在，检查交货详细信息表:

```sql
SELECT * FROM DeliveryDetails;

```

**输出:**

| DeliveryId | 产品 id | 产品名称 | 交货时间 |
| --- | --- | --- | --- |
| one | One million ten thousand and one | dell inspiron 灵越 | 2020-10-09 18:17:31 |