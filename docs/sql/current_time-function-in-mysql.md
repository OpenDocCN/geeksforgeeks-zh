# MySQL 中的 CURRENT_TIME()函数

> 原文:[https://www . geesforgeks . org/current _ time-function-in-MySQL/](https://www.geeksforgeeks.org/current_time-function-in-mysql/)

**MySQL 中的 CURRENT_TIME()** 函数用于检查当前时间。它以 **'hh:mm:ss'** 或 **hhmmss** 格式的值返回当前时间，具体取决于该函数是在字符串还是数字上下文中使用。

**语法:**

```sql
CURRENT_TIME
    OR
CURRENT_TIME(precision)

```

**参数:**
此方法接受一个参数。

*   **精度–**
    它指定返回的分数秒精度。如果用户省略了精度参数，结果将排除精度。

**返回:**返回当前时间。

**示例-1 :**
使用 CURRENT_TIME 函数获取当前时间。

```sql
SELECT CURRENT_TIME as Curr_time ;

```

**输出:**

| 当前时间 |
| --- |
| 14:03:29 |

**示例-2 :**
使用 CURRENT_TIME 函数获取当前时间，精度设置为 5。

```sql
SELECT CURRENT_TIME(5) as Curr_time ;

```

**输出:**

| 当前时间 |
| --- |
| 14:07:10.02423 |

**示例-3 :**
使用 CURRENT_TIME 函数获取数字格式的当前时间。

```sql
SELECT CURRENT_TIME + 0  as Curr_time ;

```

**输出:**

| 当前时间 |
| --- |
| One hundred and forty thousand nine hundred and seventeen |

**示例-4:**
CURRENT _ TIME 函数可用于设置列的值。为了演示，创建一个名为 DeliveryDetails 的表。

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

在这里，我们将使用当前日期和当前时间功能，当交付将完成。“交付时间”列中的值将是当前时间给出的值，而“交付日期”列中的值将是当前日期函数给出的值。

```sql
INSERT INTO  
DeliveryDetails(ProductId, ProductName, Delivered_At, Delivered_On)
VALUES
(101, 'Let Us C', CURRENT_TIME, CURRENT_DATE);

```

现在，检查交货详细信息表:

```sql
SELECT * FROM DeliveryDetails;

```

**输出:**

| DeliveryId | 产品 id | 产品名称 | 交货时间 | 送达时间 |
| --- | --- | --- | --- | --- |
| one | One hundred and one | 让我们 C | 14:41:59 | 2020-10-01 |