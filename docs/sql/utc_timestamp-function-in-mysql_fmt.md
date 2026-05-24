# MySQL 中的 `UTC_TIMESTAMP()` 函数

> 原文: [https://www.geeksforgeeks.org/utc_timestamp-function-in-mysql/](https://www.geeksforgeeks.org/utc_timestamp-function-in-mysql/)

`UTC_TIMESTAMP()` 函数用于检查当前协调世界时(UTC)的日期和时间值。它以 `YYYY-MM-DD HH:MM:SS` 或 `YYYYMMDDHHMMSS.uuuuuu` 格式返回当前 UTC 日期和时间值，具体取决于该函数是在字符串还是数字上下文中使用。

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
使用 `UTC_TIMESTAMP` 函数获取当前 UTC 日期和时间。

```sql
SELECT UTC_TIMESTAMP as CurrUtcDateAndTime;
```

**输出:**

| CurrUtcDateAndTime |
| --- |
| 2020-10-09 18:08:13 |

**示例-2 :**
使用 `UTC_TIMESTAMP` 函数以数字格式获取当前 UTC 日期和时间。

```sql
SELECT UTC_TIMESTAMP + 0 as CurrUtcDateAndTime;
```

**输出:**

| CurrUtcDateAndTime |
| --- |
| 20201009180940 |

**示例-3 :**
可以使用 `UTC_TIMESTAMP` 函数设置列的值。为了演示，创建一个名为 `DeliveryDetails` 的表。

```sql
CREATE TABLE DeliveryDetails (
    DeliveryId INT AUTO_INCREMENT,
    ProductId INT NOT NULL,
    ProductName VARCHAR(20) NOT NULL,
    Delivered_At TIMESTAMP NOT NULL,
    PRIMARY KEY(DeliveryId)
);
```

在这里，我们将使用 `UTC_TIMESTAMP` 函数来完成交付。`Delivered_At` 列中的值将是 `UTC_TIMESTAMP` 函数给出的值。

```sql
INSERT INTO DeliveryDetails(ProductId, ProductName, Delivered_At)
VALUES (1010001, 'Dell Inspirion', UTC_TIMESTAMP);
```

现在，检查交货详细信息表:

```sql
SELECT * FROM DeliveryDetails;
```

**输出:**

| DeliveryId | ProductId | ProductName | Delivered_At |
| --- | --- | --- | --- |
| 1 | 1010001 | Dell Inspirion | 2020-10-09 18:17:31 |