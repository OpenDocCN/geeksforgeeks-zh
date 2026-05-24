# MySQL 中的 COUNT()函数

> 原文:[https://www.geeksforgeeks.org/count-function-in-mysql/](https://www.geeksforgeeks.org/count-function-in-mysql/)

**COUNT()功能:**

[MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中的这个函数用于查找从所选查询返回的索引数量。

**功能:**

*   This function is used to find the number of indexes returned by the selected query.
*   This function belongs to numerical function.
*   This function accepts only one parameter, namely an expression.
*   The function ignores null values and does not calculate them.

**语法:**

```sql
COUNT(expression)
```

**参数:**

此方法只接受一个参数，如下所示:

*   **Expression:** The specified expression can be a value of field or string type.

**返回:**

它返回从所选查询返回的索引数。

**示例-1 :**

使用 COUNT()函数并获取输出。

```sql
CREATE TABLE product
(  
user_id int NOT NULL AUTO_INCREMENT,  
product_1 VARCHAR(10),
product_2 VARCHAR(10),
price int , 
PRIMARY KEY(user_id)  
);
INSERT product(product_1, price)  
VALUES ('rice', 400);

INSERT product(product_2, price)  
VALUES ('grains', 600);

SELECT COUNT(user_id) FROM product;
```

**输出:**

```sql
2
```

**示例-2 :**

使用 COUNT()函数并计算浮点值。

```sql
CREATE TABLE floats
(  
user_id int NOT NULL AUTO_INCREMENT,  
float_val float,
PRIMARY KEY(user_id)  
);
INSERT floats(float_val)  
VALUES (3.5);

INSERT floats(float_val)  
VALUES (2.1);

INSERT floats(float_val)  
VALUES (6.3);

INSERT floats(float_val)  
VALUES (9.9);

INSERT floats(float_val)  
VALUES (7.0);

SELECT COUNT(float_val) FROM floats;
```

**输出:**

```sql
5
```

**示例-3 :**

使用 COUNT()函数，得到物料需求计划大于物料需求计划数量的输出。

```sql
CREATE TABLE package
(  
user_id int NOT NULL AUTO_INCREMENT,  
item VARCHAR(10),
mrp int,
PRIMARY KEY(user_id)    
);
INSERT package(item, mrp)  
VALUES ('book1', 3);

INSERT package(item, mrp)  
VALUES ('book2', 350);

INSERT package(item, mrp)  
VALUES ('book3', 400);

SELECT * FROM package
WHERE mrp > (SELECT COUNT(mrp) FROM package);
```

**输出:**

```sql
 user_id  | item     | mrp
--------------------------------
  2       | book2    | 350
--------------------------------
  3       | book3    | 400
```

**示例-4 :**

使用 COUNT()函数并获取(物料需求计划-销售价格)的记录。

```sql
CREATE TABLE package01
(  
user_id int NOT NULL AUTO_INCREMENT,  
item VARCHAR(10),
mrp int,
sp int,
PRIMARY KEY(user_id)    
);
INSERT package01(item, mrp, sp)  
VALUES ('book1', 250, 240);

INSERT package01(item, mrp, sp)  
VALUES ('book2', 350, 320);

INSERT package01(item, mrp)  
VALUES ('book3', 400);

SELECT COUNT(mrp-sp) FROM package01;
```

**输出:**

```sql
2
```

**应用:**

该函数用于查找从所选查询返回的索引数量。