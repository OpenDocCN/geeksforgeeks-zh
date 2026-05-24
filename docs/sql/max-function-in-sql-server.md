# SQL Server 中的 MAX()函数

> 原文:[https://www.geeksforgeeks.org/max-function-in-sql-server/](https://www.geeksforgeeks.org/max-function-in-sql-server/)

**MAX() :**

SQL Server 中的此函数用于查找所述值组中的最大值。

**特征:**

*   该函数用于寻找最大值。
*   该函数属于数值函数。
*   这个函数只接受一个参数，即表达式。

**语法:**

```sql
MAX(expression)
```

**参数:**

此方法接受一个参数。

*   **表达式–**
    指定的数值，可以是字段或给定的公式。

**返回:**

它返回指定值组中的最大值。

**示例-1 :**

使用 MAX()函数并获取输出。

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

SELECT MAX(price) FROM product;
```

**输出:**

```sql
600
```

**示例-2 :**

使用 MAX()函数并找到所述浮点值的最大值。

```sql
CREATE TABLE floats
(  
user_id int IDENTITY(100, 2) NOT NULL,
float_val float
);
INSERT floats(float_val)  
VALUES (3.5);

INSERT floats(float_val)  
VALUES (2.1);

INSERT floats(float_val)  
VALUES (6.3);

INSERT floats(float_val)  
VALUES (9.0);

INSERT floats(float_val)  
VALUES (7.0);

SELECT MAX(float_val) FROM floats;
```

**输出:**

```sql
9
```

**示例-3 :**

使用 MAX()函数，得到物料需求计划小于所有物料需求计划最大值的输出。

```sql
CREATE TABLE package
(  
user_id int IDENTITY(100, 4) NOT NULL,  
item VARCHAR(10),
mrp int  
);
INSERT package(item, mrp)  
VALUES ('book1', 3);

INSERT package(item, mrp)  
VALUES ('book2', 350);

INSERT package(item, mrp)  
VALUES ('book3', 400);

SELECT * FROM package
WHERE mrp < (SELECT MAX(mrp) FROM package);
```

**输出:**

```sql
  | user_id  | item     | mrp
--------------------------------
1 | 100      | book1    | 3
--------------------------------
2 | 104      | book2    | 350
```

**示例-4 :**

使用 MAX()函数，获取所有(物料需求计划-销售价格)值的最大值。

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

SELECT MAX(mrp-sp) FROM package;
```

**输出:**

```sql
50
```

**应用:**

该函数用于查找所有规定值的最大值。