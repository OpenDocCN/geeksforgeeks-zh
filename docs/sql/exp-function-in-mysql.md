# MySQL 中的 EXP()函数

> 原文:[https://www.geeksforgeeks.org/exp-function-in-mysql/](https://www.geeksforgeeks.org/exp-function-in-mysql/)

**EXP()** 函数在 MySQL 中用来返回 E 的升到指定数的幂。这里 E(2.718281…)是自然对数的底数。

**语法:**

```sql
EXP(X)

```

**参数:**该方法接受语法中如上所述的一个参数，描述如下:

**X–**将用作 e 的幂的指定数字

**返回:**返回 E，E 的幂等于给定数 x

**示例-1 :**
使用 EXP()函数计算 e 的 1 次方。

```sql
SELECT EXP(1) AS Exp_Val ;

```

**输出:**

| EXP_VAL |
| --- |
| 2.718281828459045 |

**示例-2 :**
使用 EXP()函数计算 e 升至-3 的幂。

```sql
SELECT EXP(-3) AS Exp_Val ;

```

**输出:**

| EXP_VAL |
| --- |
| 0.049787068367863944 |

**示例-3:**
EXP 函数也可以用在一列数据中。演示创建一个名为“产品”的表。

```sql
CREATE TABLE Product(
Product_id INT AUTO_INCREMENT,  
Product_name VARCHAR(100) NOT NULL,
Buying_price DECIMAL(13, 2) NOT NULL,
Selling_price DECIMAL(13, 2) NOT NULL,
Service_grade Decimal(6, 2) NOT NULL,
PRIMARY KEY(Product_id)
);

```

**现在向产品表中插入一些数据–**

```sql
INSERT INTO  
Product(Product_name, Buying_price, Selling_price, Service_grade)
VALUES
('ASUS ROG', 80000.00, 100000.00, 4.00 ),
('DELL INSPIRON', 75000.00, 90000.00, 3.00 ),
('ACER PREDATOR', 100000.00, 134000.00, 2.50 ),
('LENOVO LEGION', 90000.00, 118000.00, 1.50 ),
('HP OMEN', 70000.00, 85000.00, 5.00) ;

```

**显示产品表中的所有数据–**

```sql
Select * from Product;

```

| 产品标识 | 产品名称 | BUYING_PRICE | 销售价格 | 服务等级 |
| --- | --- | --- | --- | --- |
| one | 华硕罗格 | Eighty thousand | One hundred thousand | Four |
| Two | 戴尔灵越 | Seventy-five thousand | Ninety thousand | Three |
| three | 宏碁捕食者 | One hundred thousand | One hundred and thirty-four thousand | Two point five |
| four | 联想军团 | Ninety thousand | One hundred and eighteen thousand | One point five |
| five | 惠普企业名称 | Seventy thousand | Eighty-five thousand | Five |

现在，我们将查找 Service_grade 列中所有记录的 exp 值。

```sql
Select Product_id, Product_name, Buying_price,  
Selling_price, Service_grade,
EXP(Service_grade) AS EXPGRADE  
FROM Product;

```

**输出:**

| 产品标识 | 产品名称 | BUYING_PRICE | 销售价格 | 服务等级 | 提升 |
| --- | --- | --- | --- | --- | --- |
| one | 华硕罗格 | Eighty thousand | One hundred thousand | Four | 54.598150033144236 |
| Two | 戴尔灵越 | Seventy-five thousand | Ninety thousand | Three | 20.085536923187668 |
| three | 宏碁捕食者 | One hundred thousand | One hundred and thirty-four thousand | Two point five | 12.182493960703473 |
| four | 联想军团 | Ninety thousand | One hundred and eighteen thousand | One point five | 4.4816890703380645 |
| five | 惠普企业名称 | Seventy thousand | Eighty-five thousand | Five | 148.4131591025766 |