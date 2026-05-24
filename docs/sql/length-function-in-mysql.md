# MySQL 中的 LENGTH()函数

> 原文:[https://www.geeksforgeeks.org/length-function-in-mysql/](https://www.geeksforgeeks.org/length-function-in-mysql/)

**LENGTH() :**

[MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中的这个函数是用来查找字节类型的字符串长度的。

**特征:**

*   该函数用于查找字节类型的字符串长度。
*   该函数属于字符串函数。
*   这个函数只接受一个参数，即字符串。
*   该函数只返回字节长度。

**语法:**

```sql
LENGTH(string)
```

**参数:**

此方法只接受一个参数。

*   **字符串–**
    指定的字符串，其长度将被计数。

**返回:**

它返回字节类型的字符串长度。

**示例-1 :**

使用 LENGTH()函数并获取输出。

```sql
SELECT LENGTH("GEEKSFORGEEKS");
```

**输出:**

```sql
13
```

**示例-2 :**

使用 LENGTH()函数并找到所有浮点值的长度。

```sql
CREATE TABLE float061
(  
user_id int NOT NULL AUTO_INCREMENT,
float_val float,
PRIMARY KEY(user_id)
);
INSERT float061(float_val)  
VALUES (1.9);

INSERT float061(float_val)  
VALUES (1.1);

INSERT float061(float_val)  
VALUES (3.9);

INSERT float061(float_val)  
VALUES (10.2);

INSERT float061(float_val)  
VALUES (7.9);

SELECT LENGTH(float_val) FROM float061;
```

**输出:**

```sql
    | LENGTH(float_val)|     
-----------------------------
    |         3        | 
-----------------------------
    |         3        | 
-----------------------------
    |         3        |
-----------------------------
    |         4        |
-----------------------------
    |         3        |
```

**示例-3 :**

使用 LENGTH()函数并获取给定项目的长度。

```sql
CREATE TABLE package099
(  
user_id int NOT NULL AUTO_INCREMENT,
item VARCHAR(10),
mrp int,
PRIMARY KEY(user_id)
);
INSERT package099(item, mrp)  
VALUES ('books', 350);

SELECT LENGTH(item) FROM package099;
```

**输出:**

```sql
5
```

**示例-4 :**

使用 LENGTH()函数并获取所有(MRP+销售价格)值的长度。

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
VALUES ('book1', 250, 245);

INSERT package72(item, mrp, sp)  
VALUES ('book2', 350, 345);

INSERT package72(item, mrp, sp)  
VALUES ('book3', 400, 350);

SELECT LENGTH(mrp+sp) FROM package72;
```

**输出:**

```sql
    |  LENGTH(mrp+sp) |      
-----------------------------
    |         3       | 
-----------------------------
    |         3       | 
-----------------------------
    |         3       |
```

**应用:**

该函数用于查找字节类型的字符串长度。