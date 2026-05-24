# SQL Server 中的 AVG()函数

> 原文:[https://www.geeksforgeeks.org/avg-function-in-sql-server/](https://www.geeksforgeeks.org/avg-function-in-sql-server/)

**AVG() :**

SQL Server 中的此函数用于返回指定表达式的平均值。

**特征:**

*   This function is used to average the specified expression.
*   This function belongs to numerical function.
*   This function accepts only one parameter, namely an expression.
*   The function ignores null values.

**语法:**

```sql
AVG(expression)
```

**参数:**

此方法接受一个参数。

*   **Expression-** The specified value can be a specified field or a specified formula.

**返回:**

它返回指定表达式的平均值。

**示例-1 :**

使用 AVG()函数并获取输出。

```sql
CREATE TABLE product
(  
user_id int IDENTITY(100, 2) NOT NULL,    
product_1 VARCHAR(10),
product_2 VARCHAR(10),
price int  
);
INSERT product(product_1, price)  
VALUES ('rice', 400);

INSERT product(product_2, price)  
VALUES ('grains', 600);

SELECT AVG(price) FROM product;
```

**输出:**

```sql
500
```

这里，返回第一个产品价格和第二个产品价格的平均值。

**示例-2 :**

使用 AVG()函数并获取浮点值的平均值。

```sql
CREATE TABLE floats
(  
user_id int IDENTITY(100, 2) NOT NULL,
float_val float
);
INSERT floats(float_val)  
VALUES (3.5);

INSERT floats(float_val)  
VALUES (2.5);

SELECT AVG(float_val) FROM floats;
```

**输出:**

```sql
3
```

**示例-3 :**

使用 AVG()函数，得到物料需求计划大于产品平均物料需求计划的输出。

```sql
CREATE TABLE package
(  
user_id int IDENTITY(100, 4) NOT NULL,  
item VARCHAR(10),
mrp int  
);
INSERT package(item, mrp)  
VALUES ('book1', 250);

INSERT package(item, mrp)  
VALUES ('book2', 350);

INSERT package(item, mrp)  
VALUES ('book3', 400);

SELECT * FROM package
WHERE mrp > (SELECT AVG(mrp) FROM package);
```

**输出:**

```sql
  | user_id  | item     | mrp
--------------------------------
1 | 104      | book2    | 350
--------------------------------
2 | 108      | book3    | 400
```

**示例-4 :**

使用 AVG()函数并获得(物料需求计划-销售价格)的平均值。

```sql
CREATE TABLE package
(  
user_id int IDENTITY(100, 4) NOT NULL,  
item VARCHAR(10),
mrp int,
sp int
);
INSERT package(item, mrp, sp)  
VALUES ('book1', 250, 240);

INSERT package(item, mrp, sp)  
VALUES ('book2', 350, 320);

INSERT package(item, mrp, sp)  
VALUES ('book3', 400, 350);

SELECT AVG(mrp-sp) FROM package;
```

**输出:**

```sql
30
```

**应用:**

该函数用于求指定表达式的平均值。