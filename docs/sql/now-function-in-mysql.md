# MYSQL 中的 NOW()函数

> 原文:[https://www.geeksforgeeks.org/now-function-in-mysql/](https://www.geeksforgeeks.org/now-function-in-mysql/)

**NOW() :**
这个在 MySQL 中的[功能是用来检查当前日期时间值的。NOW()函数的返回类型可以是' YYYY-MM-DD HH:MM:SS '格式，也可以是 YYYYMMDDHHMMSS.uuuuuu 格式，具体取决于该函数是在字符串还是数字上下文中使用。](https://www.geeksforgeeks.org/sql-functions-aggregate-scalar-functions/)

**语法:**

```sql
NOW()
```

**参数:**
此方法不接受任何参数。

**返回:**
返回当前日期时间值。

**示例-1 :**
使用 NOW 函数查找当前日期和时间。在这里，我们将获得‘YYYY-MM-DD HH:MM:SS’格式的结果。

```sql
SELECT NOW() 
as CurrDateTime ;
```

**输出:**

<figure class="table">

| 当前日期时间 |
| --- |
| 2020-11-26 18:37:42 |

</figure>

**示例-2 :**
使用数值格式的 NOW 函数获取当前日期和时间。这里的结果将是 YYYYMMDDHHMMSS.uuuuuu 格式。

```sql
SELECT NOW()+ 0 
as CurrDateTime ;
```

**输出:**

<figure class="table">

| 当前日期时间 |
| --- |
| 20201126183839 |

</figure>

**示例-3 :**
我们也可以使用 NOW 函数来设置列的值。为了演示，创建一个名为 DeliveryDetails 的表。

```sql
CREATE TABLE Product (
ProductId INT NOT NULL,
ProductName VARCHAR(20) NOT NULL,
Delivered_At TIMESTAMP NOT NULL,
PRIMARY KEY(ProductId)
);
```

在这里，我们将使用现在功能，当交付将完成。“交货时间”列中的值将是“现在功能”给出的值。

```sql
INSERT INTO  
Product (ProductId, ProductName, Delivered_At)
VALUES
(1010, 'Apple MacBook', NOW());
```

现在，检查产品表:

```sql
SELECT * FROM Product;
```

**输出:**

<figure class="table">

| 产品 id | 产品名称 | delived _ AT |
| --- | --- | --- |
| One thousand and ten | 苹果 MacBook | 2021-10-01 14:41:15 |

</figure>