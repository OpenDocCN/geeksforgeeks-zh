# MySQL 中的 UUID_SHORT()函数

> 原文:[https://www.geeksforgeeks.org/uuid_short-function-in-mysql/](https://www.geeksforgeeks.org/uuid_short-function-in-mysql/)

MySQL 中的这个函数用于以 64 位无符号整数的形式返回一个“短”通用标识符。如果满足以下条件，UUID _ 肖特()的值保证是唯一的:

1.  当前服务器的 server_id 值介于 0 和 255 之间，并且在我们的源服务器和副本服务器集中是唯一的。
2.  我们不会在 mysqld 重启之间为我们的服务器主机设置系统时间。
3.  在 mysqld 重启之间，我们应该平均每秒调用 UUID_SHORT()不到 1600 万次。

**语法:**

```sql
UUID_SHORT()
```

**参数:**
这个方法没有任何参数。

**返回:**
返回一个通用唯一标识号。

**示例-1 :**
借助 UUID_SHORT 函数生成短的通用唯一标识符值。

```sql
SELECT UUID_SHORT() AS Short_UUID_Value ;

```

**输出:**

| 短 _ UUID _ 价值 |
| --- |
| 99032629508046848 |

**示例-2 :**
每当我们使用 UUID_SHORT 函数时，我们都会得到不同的 SHORT Universal Identifier 值。让我们检查一下–

```sql
SELECT UUID_SHORT() 
AS  SHORT_UUID_VALUE1, UUID_SHORT() 
AS SHORT_UUID_VALUE2, UUID_SHORT() 
AS SHORT_UUID_VALUE3 ;

```

**输出:**

| 肖特 _ UUID _ 值 1 | 肖特 _ UUID _ 值 2 | 肖特 _ UUID _ 值 3 |
| --- | --- | --- |
| 99032629508046849 | 99032629508046850 | 99032629508046851 |

**示例-3 :**
在本例中，我们将使用 UUID_SHORT 作为表中的主键。为了演示，创建一个名为 OrderDetails 的表。

```sql
CREATE TABLE OrderDetails2(
  OrderId BIGINT PRIMARY KEY,
  ProductName VARCHAR(100) NOT NULL,
  Price DECIMAL(10, 2) NOT NULL,
  ExpectedDelivery DATE NOT NULL
);
```

现在，将数据插入 OrderDetails 表。在这里，我们将使用 UUID _ 肖特函数来分配 OrderId 列中的值。

```sql
INSERT INTO OrderDetails2(OrderId, ProductName, Price, ExpectedDelivery)
VALUES(UUID_SHORT(), 'Asus Rog', 90000.00, '2020-12-20'),
     (UUID_SHORT(), 'Acer Predator', 100000.00, '2020-12-18'),
     (UUID_SHORT(), 'Lenovo Legion', 85000.00, '2020-12-19'),
     (UUID_SHORT(), 'Hp Omen', 70000.00, '2020-12-18'),
     (UUID_SHORT(), 'Dell Inspiron', 65000.00, '2020-12-23'),
     (UUID_SHORT(), 'Acer Nitro', 60000.00, '2020-12-22'),
     (UUID_SHORT(), 'Asus Tuf', 80000.00, '2020-12-19');
```

接下来，我们将使用以下命令来检查该表。

```sql
SELECT  * from OrderDetails2;

```

**输出:**

| ORDERID(订单 ID) | 产品名称 | 价格 | 预期交货 |
| --- | --- | --- | --- |
| 99032629508046854 | 华硕罗格 | Ninety thousand | 2020-12-20 |
| 99032629508046855 | 宏基掠夺者 | One hundred thousand | 2020-12-18 |
| 99032629508046856 | 联想军团 | Eighty-five thousand | 2020-12-19 |
| 99032629508046857 | 惠普企业名称 | Seventy thousand | 2020-12-18 |
| 99032629508046858 | 戴尔灵越 | Sixty-five thousand | 2020-12-23 |
| 99032629508046859 | 宏碁硝基 | Sixty thousand | 2020-12-22 |
| 99032629508046860 | 华硕塔夫 | Eighty thousand | 2020-12-19 |