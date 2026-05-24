# MySQL 中的 UUID()函数

> 原文:[https://www.geeksforgeeks.org/uuid-function-in-mysql/](https://www.geeksforgeeks.org/uuid-function-in-mysql/)

[MySQL](https://www.geeksforgeeks.org/mysql-common-mysql-queries/) 中的这个函数用来返回一个根据 RFC 4122“一个通用唯一标识符(UUID) URN 命名空间”生成的通用唯一标识符(UUID)。它被设计成一个普遍唯一的数字。两个 UUID 值应该是不同的，即使它们是在两个独立的服务器上生成的。在 MySQL 中，UUID 值是表示为 utf8 字符串的 128 位数字，十六进制数字的格式如下。

**示例–**

```sql
aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee

```

这里，前三个数字是从时间戳的低、中和高部分生成的。如您所见，在上述格式中，第四位数字代码将保持时间唯一性，第五位代码将提供空间唯一性，并且它是一个 IEEE 802 节点号。

**语法:**

```sql
UUID()
```

**参数:**
这个方法没有任何参数。
**返回:**
返回一个通用唯一标识号。

**示例-1 :**
借助 UUID 函数生成通用唯一标识符值。

```sql
SELECT UUID() 
AS UUID_Value ;
```

**输出:**

| UUID _ 价值 |
| --- |
| FBE 516 f 6-3 和 39-11eb-b897-0862660ccbd4 |

**示例-2 :**
每当我们使用 UUID 函数时，我们都会得到不同的通用唯一标识符值。让我们检查一下。

```sql
  SELECT UUID() 
AS  
UUID_VALUE1, 
UUID() 
AS UUID_VALUE2, 
UUID() 
AS UUID_VALUE3 ;
```

**输出:**

| UUID _ 值 1 | UUID _ 价值 2 | UUID _ 价值 3 |
| --- | --- | --- |
| e 762634 c-3e 41-11eb- b897-0862660 ccbd 4 | e 7626367-3 和 41-11eb-b897-0862660ccbd4 | e 7626368-3 和 41-11eb-b897-0862660ccbd4 |

**示例-3 :**
在本例中，我们将使用 UUID 作为表中的主键。为了演示，创建一个名为 OrderDetails 的表。

```sql
CREATE TABLE OrderDetails(
   OrderId BINARY(16) PRIMARY KEY,
   ProductName VARCHAR(100) NOT NULL,
   Price DECIMAL(10, 2) NOT NULL,
   ExpectedDelivery DATE NOT NULL
);

```

现在，将数据插入 OrderDetails 表。在这里，我们将使用 UUID 和 UUID 的函数来指定 OrderId 列中的值。

```sql
INSERT INTO OrderDetails(OrderId, ProductName, Price, ExpectedDelivery)
VALUES(UUID_TO_BIN(UUID()), 'Asus Rog', 90000.00, '2020-12-20'),
      (UUID_TO_BIN(UUID()), 'Acer Predator', 100000.00, '2020-12-18'),
      (UUID_TO_BIN(UUID()), 'Lenovo Legion', 85000.00, '2020-12-19'),
      (UUID_TO_BIN(UUID()), 'Hp Omen', 70000.00, '2020-12-18'),
      (UUID_TO_BIN(UUID()), 'Dell Inspiron', 65000.00, '2020-12-23'),
      (UUID_TO_BIN(UUID()), 'Acer Nitro', 60000.00, '2020-12-22'),
      (UUID_TO_BIN(UUID()), 'Asus Tuf', 80000.00, '2020-12-19');
```

接下来，我们将使用以下命令来检查该表。

```sql
SELECT  * from OrderDetails;
```

**输出:**

| ORDERID(订单 ID) | 产品名称 | 价格 | 预期交货 |
| --- | --- | --- | --- |
| 0x 50 ef 0d93 E3 和 11 具有 8970862660CCBD4 | 华硕罗格 | Ninety thousand | 2020-12-20 |
| 0xe 514 f 3293 E3 和 11 具有 8970862660CCBD4 | 宏基掠夺者 | One hundred thousand | 2020-12-18 |
| 0xe 514 f 6793 E3 和 11 具有 8970862660CCBD4 | 联想军团 | Eighty-five thousand | 2020-12-19 |
| 0xe 514 F7 c83 E3 和 11 ebb 8970862660 ccbd 4 | 惠普企业名称 | Seventy thousand | 2020-12-18 |
| 0xe 514 f 9173 E3 和 11 ebb 8970862660 ccbd 4 | 戴尔灵越 | Sixty-five thousand | 2020-12-23 |
| 0xe 514 fa 7 B3 和 3 及 11 具有 8970862660CCBD4 | 宏碁硝基 | Sixty thousand | 2020-12-22 |
| 0xe 514 fc 6 C3 和 3 及 11 具有 8970862660CCBD4 | 华硕塔夫 | Eighty thousand | 2020-12-19 |