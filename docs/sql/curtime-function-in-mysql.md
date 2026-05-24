# MySQL 中的 CURTIME()函数

> 原文:[https://www.geeksforgeeks.org/curtime-function-in-mysql/](https://www.geeksforgeeks.org/curtime-function-in-mysql/)

[MySQL](https://www.geeksforgeeks.org/mysql-common-mysql-queries/) 中的**CURTME()**功能用于查看当前时间。它以 **'hh:mm:ss'** 或 **'hhmmss'** 格式的值返回当前时间，具体取决于该函数是在字符串还是数字上下文中使用。

**语法:**

```sql
CURTIME(fsp)
```

**参数:**

此方法只接受一个参数。

**FSP–**
它指定返回的分数秒精度。如果用户省略了精度参数，结果将排除精度。

**返回:**

它返回当前时间。

**示例-1:**

使用 CURTIME 函数获取当前时间。

```sql
SELECT CURTIME() as Curr_time ;
```

**输出:**

| 当前时间 |
| --- |
|  13:06:54 |

**例 2:**

使用 CURTIME 函数获取当前时间的精度设置为 3。

```sql
SELECT CURTIME(3) as Curr_time ;
```

**输出:**

| 当前时间 |
| --- |
|  13:09:06.109 |

**示例-3:**

使用数字格式的 CURTIME 函数获取当前时间。

```sql
SELECT CURTIME() + 0  as Curr_time ;
```

**输出:**

| 当前时间 |
| --- |
|  131014 |

**示例-4:**

CURTIME 函数可以用来设置列的值。为了演示，创建一个名为 DeliveryDetails 的表。

```sql
CREATE TABLE DeliveryDetails (
DeliveryId INT AUTO_INCREMENT,
ProductId INT NOT NULL,
ProductName VARCHAR(20) NOT NULL,
Delivered_At TIME NOT NULL,
Delivered_On DATE NOT NULL,
PRIMARY KEY(DeliveryId)
);
```

在这里，我们将使用 CODETATE 和 CURTIME 功能，当一个交付将完成。“交付时间”列中的值将是 CURTIME 给出的值，而“交付时间”列中的值将是 CURDATE 函数给出的值。

```sql
INSERT INTO  
DeliveryDetails(ProductId, ProductName, Delivered_At, Delivered_On)
VALUES
(12345, 'Dell Latitude', CURTIME(), CURDATE() );
```

现在，检查交货详细信息表:

```sql
SELECT * FROM DeliveryDetails;
```

**输出:**

| DELIVERYID | 产品 id | 产品名称 | 交付时间 | 已交付 _ 开 |
| --- | --- | --- | --- | --- |
| one | one two three four five | 戴尔纬度 |  13:17:22 | 2020-11-20 |