# MySQL 中的 UTC_DATE()函数

> 原文:[https://www.geeksforgeeks.org/utc_date-function-in-mysql/](https://www.geeksforgeeks.org/utc_date-function-in-mysql/)

**使用 MySQL 中的 UTC_DATE()** 函数检查当前的协调世界时(UTC)日期。它以' YYYY-MM-DD '或 YYYYMMDD 格式返回 UTC 日期值，具体取决于该函数是在字符串还是数字上下文中使用。

**语法:**

```sql
UTC_DATE
   OR
UTC_DATE()

```

**参数:**
此方法不接受任何参数。

**返回:**
返回当前协调世界时(UTC)日期。

**示例-1 :**
使用 UTC_DATE 函数获取当前 UTC 日期。

```sql
SELECT UTC_DATE as CurrUtcDate ;

```

**输出:**

| 当前日期 |
| --- |
| 2020-10-01 |

**示例-2 :**
使用数字格式的 UTC_DATE 函数获取当前时间。

```sql
SELECT UTC_DATE + 0 as CurrUtcDate ;

```

**输出:**

| 当前日期 |
| --- |
| Twenty million two hundred and one thousand and one |

**示例-3 :**
可以使用 UTC_DATE 函数设置列的值。为了演示，创建一个名为 DeliveryDetails 的表。

```sql
CREATE TABLE DeliveryDetails (
DeliveryId INT AUTO_INCREMENT,
ProductId INT NOT NULL,
ProductName VARCHAR(20) NOT NULL,
Delivered_On DATE NOT NULL,
PRIMARY KEY(DeliveryId)
);

```

在这里，我们将使用 UTC_DATE 函数来完成交付。“交货日期”列中的值将是世界协调时日期函数给出的值。

```sql
INSERT INTO  
DeliveryDetails(ProductId, ProductName, Delivered_On)
VALUES
(101001, 'Asus ROG', CURRENT_DATE);

```

现在，检查交货详细信息表:

```sql
SELECT * FROM DeliveryDetails;

```

**输出:**

| DeliveryId | 产品 id | 产品名称 | 送达时间 |
| --- | --- | --- | --- |
| one | One hundred and one thousand and one | 华硕罗格 | 2020-10-01 |