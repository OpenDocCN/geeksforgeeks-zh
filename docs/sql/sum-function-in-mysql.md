# MySQL 中的 SUM()函数

> 原文:[https://www.geeksforgeeks.org/sum-function-in-mysql/](https://www.geeksforgeeks.org/sum-function-in-mysql/)

**SUM()函数:**

[MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中的这个函数用来计算指定的一组值的和。

**特征:**

*   This function is used to calculate the sum of the specified group values.
*   This function belongs to numerical function.
*   This function accepts only one parameter, namely an expression.
*   The function ignores null values.

**语法:**

```sql
SUM(expression)
```

**参数:**

该方法只接受一个参数，如下所示:

*   **Expression:** The specified expression can be a field or a given formula.

**返回:**

它返回指定值组的总和。

**示例-1 :**

使用 SUM()函数并获取输出。

```sql
CREATE TABLE product09
(  
user_id int NOT NULL AUTO_INCREMENT,  
product_1 VARCHAR(10),
product_2 VARCHAR(10),
price int,
PRIMARY KEY(user_id)   
);
INSERT product09(product_1, price)  
VALUES ('rice', 350);

INSERT product09(product_2, price)  
VALUES ('grains', 230);

SELECT SUM(price) FROM product09;
```

**输出:**

```sql
580
```

**示例-2 :**

使用 SUM()函数，求所有指定浮点值的和。

```sql
CREATE TABLE float062
(  
user_id int NOT NULL AUTO_INCREMENT,
float_val float,
PRIMARY KEY(user_id)
);
INSERT float062(float_val)  
VALUES (1.9);

INSERT float062(float_val)  
VALUES (1.1);

INSERT float062(float_val)  
VALUES (3.9);

INSERT float062(float_val)  
VALUES (10.2);

INSERT float062(float_val)  
VALUES (7.9);

SELECT SUM(float_val) FROM float062;
```

**输出:**

```sql
25
```

**示例-3 :**

使用 SUM()函数，得到物料需求计划小于所有物料需求计划之和的输出。

```sql
CREATE TABLE package77
(  
user_id int NOT NULL AUTO_INCREMENT, 
item VARCHAR(10),
mrp int,
PRIMARY KEY(user_id) 
);
INSERT package77(item, mrp)  
VALUES ('book1', 3);

INSERT package77(item, mrp)  
VALUES ('book2', 350);

INSERT package77(item, mrp)  
VALUES ('book3', 400);

SELECT * FROM package77
WHERE mrp < (SELECT SUM(mrp) FROM package77);
```

**输出:**

```sql
 user_id | item    | mrp
--------------------------------
  1      | book1   | 3
--------------------------------
  2      | book2   | 350
--------------------------------
  3      | book3   | 400
```

**示例-4 :**

使用 SUM()函数并获取所有(物料需求计划-销售价格)值的总和。

```sql
CREATE TABLE package72
(  
user_id int NOT NULL AUTO_INCREMENT,  
item VARCHAR(10),
mrp int,
sp int,
PRIMARY KEY(user_id)
);
INSERT package72(item, mrp, sp)  
VALUES ('book1', 250, 240);

INSERT package72(item, mrp, sp)  
VALUES ('book2', 350, 320);

INSERT package72(item, mrp, sp)  
VALUES ('book3', 400, 350);

SELECT SUM(mrp-sp) FROM package72;
```

**输出:**

```sql
90
```

**应用:**

此函数用于计算指定值组的总和。