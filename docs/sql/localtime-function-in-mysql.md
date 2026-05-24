# MySQL 中的 LOCALTIME()函数

> 原文:[https://www.geeksforgeeks.org/localtime-function-in-mysql/](https://www.geeksforgeeks.org/localtime-function-in-mysql/)

**LOCALTIME**()MySQL 中的函数用于检查当前日期和时间值。它以“yyyyy-MM-DD HH:MM:SS”格式或 YYYYMMDDHHMMSS.uuuuuu 格式返回当前日期和时间的值，具体取决于该函数是在字符串还是数字上下文中使用。

**语法:**

```sql
LOCALTIME
 OR
LOCALTIME()

```

**参数:**
此方法不接受任何参数。

**返回:**
返回当前日期时间值。

**示例-1 :**
使用 LOCALTIME 函数获取当前日期和时间。

```sql
SELECT LOCALTIME as CurrDateTime ;

```

**输出:**

| CURRDATETIME |
| --- |
| 2020-10-15 13:33:54 |

**示例-2 :**
使用数字格式的 LOCALTIME 函数获取当前日期和时间。

```sql
SELECT LOCALTIME + 0 as CurrDateTime ;

```

**输出:**

| CURRDATETIME |
| --- |
| 20201015133627 |

**示例-3:**
LOCALTIME 函数可用于设置列的值。为了演示，创建一个名为 DeliveryDetails 的表。

```sql
CREATE TABLE DeliveryDetails (
DeliveryId INT AUTO_INCREMENT,
ProductId INT NOT NULL,
ProductName VARCHAR(20) NOT NULL,
Delivered_At TIMESTAMP NOT NULL,
PRIMARY KEY(DeliveryId)
);

```

在这里，我们将使用 LOCALTIME 函数，当一个交付将被完成。“交付时间”列中的值将是本地时间函数给出的值。

```sql
INSERT INTO  
DeliveryDetails(ProductId, ProductName, Delivered_At)
VALUES
(101010101, 'Asus Rog', LOCALTIME);

```

现在，检查交货详细信息表:

```sql
SELECT * FROM DeliveryDetails;

```

**输出:**

| DELIVERYID | 产品 id | 产品名称 | 交付时间 |
| --- | --- | --- | --- |
| one | One hundred and one million ten thousand one hundred and one | 华硕罗格 | 2020-10-15 13:42:47 |