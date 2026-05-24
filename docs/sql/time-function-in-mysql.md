# MySQL 中的 TIME()函数

> 原文:[https://www.geeksforgeeks.org/time-function-in-mysql/](https://www.geeksforgeeks.org/time-function-in-mysql/)

**TIME()** 函数在 MySQL 中用于从给定的时间/datetime 表达式中提取时间部分。如果表达式不是时间或日期时间值，时间函数将返回“00:00:00”。如果表达式为空，时间函数将返回空值。

**语法:**

```sql
TIME(expression)

```

**参数:**
此方法接受一个参数。

*   **表达式:**我们要从中提取时间的时间或日期时间值。

**返回:**
返回给定时间/日期时间表达式的时间部分。

**示例-1 :**
使用时间函数从日期时间表达式中提取时间，其中日期时间以 YYYY-MM-DD HH-MM-SS 的格式指定。

```sql
SELECT TIME("2019-01-10 08:14:21")as Time ;

```

**输出:**

| 时间 |
| --- |
| 08:14:21 |

**示例-2 :**
使用时间函数从日期时间表达式中提取时间，其中日期时间以 HH-MM-SS 的格式指定。

```sql
SELECT TIME("18:24:23")as Time ;

```

**输出:**

| 时间 |
| --- |
| 18:24:23 |

**示例-3 :**
使用时间函数从不是日期时间的表达式中提取时间。

```sql
SELECT TIME(NULL) AS TIME;

```

**输出:**

| 时间 |
| --- |
| 空 |

**示例-4 :**
时间功能可用于设置列的值。为了演示，创建一个名为 DeliveryDetails 的表。

```sql
CREATE TABLE DeliveryDetails (
DeliveryId INT AUTO_INCREMENT,
ProductId INT NOT NULL,
ProductName VARCHAR(20) NOT NULL,
Delivered_At TIME NOT NULL,
PRIMARY KEY(DeliveryId)
);
```

在这里，我们将使用时间功能时，将完成交付。“交付时间”列中的值将是时间函数给出的值。

```sql
INSERT INTO  
DeliveryDetails(ProductId, ProductName, Delivered_At)
VALUES
(12345, 'Let Us Java', TIME (NOW()));

```

现在，检查交货详细信息表:

```sql
SELECT * FROM DeliveryDetails;

```

**输出:**

| DELIVERYID | 产品 id | 产品名称 | 交付时间 |
| --- | --- | --- | --- |
| one | one two three four five | 让我们使用 Java | 09:48:34 |