# MySQL 中的 UTC_TIME()函数

> 原文:[https://www.geeksforgeeks.org/utc_time-function-in-mysql/](https://www.geeksforgeeks.org/utc_time-function-in-mysql/)

**UTC _ TIME**()MySQL 中的函数用于检查当前的协调世界时(UTC)时间值。它以“HH:MM:SS”或“HHMMSS”格式返回世界协调时时间值，具体取决于该函数是在字符串还是数字上下文中使用。

**语法:**

```sql
UTC_TIME
  OR
UTC_TIME()

```

**参数:**
此方法不接受任何参数。

**返回:**
返回当前 UTC 时间值。

**示例-1 :**
使用 UTC_TIME 函数获取当前 UTC 时间。

```sql
SELECT UTC_TIME as CurrUtcTime ;

```

**输出:**

| 当前时间 |
| --- |
| 18:11:35 |

**示例-2 :**
使用数字格式的 UTC_TIME 函数获取当前 UTC 时间。

```sql
SELECT UTC_TIME + 0 as CurrUtcTime ;

```

**输出:**

| 当前时间 |
| --- |
| One hundred and eighty-one thousand two hundred and fifty |

**示例-3 :**
可以使用 UTC_TIME 函数设置列的值。为了演示，创建一个名为 DeliveryDetails 的表。

```sql
CREATE TABLE DeliveryDetails (
DeliveryId INT AUTO_INCREMENT,
ProductId INT NOT NULL,
ProductName VARCHAR(20) NOT NULL,
Delivered_On DATE NOT NULL,
Delivered_At TIME NOT NULL,
PRIMARY KEY(DeliveryId)
);

```

在这里，我们将使用世界协调时 _ 日期和世界协调时 _ 时间功能，当交付将完成。“交付时间”列中的值将是世界协调时 _ 日期函数给出的值，而“交付时间”列中的值将是世界协调时 _ 时间函数给出的值。

```sql
INSERT INTO  
DeliveryDetails(ProductId, ProductName, Delivered_On, Delivered_At)
VALUES
(900000001, 'Lenovo Legion', UTC_DATE, UTC_TIME);

```

现在，检查交货详细信息表:

```sql
SELECT * FROM DeliveryDetails;

```

**输出:**

| DeliveryId | 产品 id | 产品名称 | 送达时间 | 交货时间 |
| --- | --- | --- | --- | --- |
| one | Nine hundred million and one | 联想军团 | 2020-10-08 | 18:25:59 |