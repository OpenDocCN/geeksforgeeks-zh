# MySQL 中的 AVG()函数

> 原文:[https://www.geeksforgeeks.org/avg-function-in-mysql/](https://www.geeksforgeeks.org/avg-function-in-mysql/)

**AVG()功能:**

[MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中的这个函数用来返回指定表达式的平均值。

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

此方法只接受一个参数，如下所示。

*   **Expression-** The specified value can be a specified field or a specified formula.

**返回:**

它返回指定表达式的平均值。

**示例-1 :**

使用 AVG()函数并获取输出。

**创建表格–**

```sql
CREATE TABLE item13
(  
user_id int,    
product01 VARCHAR(4),
product02 VARCHAR(10),
price int  
);
```

**插入数据–**

```sql
INSERT item13(product01, price)  
VALUES ('rice', 500);

INSERT item13(product02, price)  
VALUES ('grains', 700);
```

**读取数据–**

```sql
SELECT AVG(price) FROM item13;
```

**输出:**

```sql
600
```

这里，返回第一个产品价格和第二个产品价格的平均值。

**示例-2 :**

使用 AVG()函数并获取浮点值的平均值。

**创建表格–**

```sql
CREATE TABLE floats
(  
user_id int,
float_val float
);
```

**插入数据–**

```sql
INSERT floats(float_val)  
VALUES (3.5);

INSERT floats(float_val)  
VALUES (2.5);
```

**读取数据–**

```sql
SELECT AVG(float_val) FROM floats;
```

**输出:**

```sql
3
```

**示例-3 :**

使用 AVG()函数，得到物料需求计划大于产品平均物料需求计划的输出。

**创建表格–**

```sql
CREATE TABLE package01
(  
user_id int NOT NULL AUTO_INCREMENT,  
item VARCHAR(10),
mrp int, 
PRIMARY KEY(user_id)  
);
```

**插入数据–**

```sql
INSERT package01(item, mrp)  
VALUES ('book1', 250);

INSERT package01(item, mrp)  
VALUES ('book2', 350);

INSERT package01(item, mrp)  
VALUES ('book3', 400);
```

**读取数据–**

```sql
SELECT * FROM package01
WHERE mrp > (SELECT AVG(mrp) FROM package01);
```

**输出:**

<figure class="table">

| 【用户 _ id】 | 【项目】 |
| --- | --- |
| 【2】 |

</figure>

**示例-4 :**

使用 AVG()函数并获得(物料需求计划-销售价格)的平均值。

**创建表格–**

```sql
CREATE TABLE package011
(  
user_id int NOT NULL AUTO_INCREMENT,  
item VARCHAR(10) NOT NULL,
mrp int NOT NULL,
sp int NOT NULL,
PRIMARY KEY(user_id)  
);
```

**插入数据–**

```sql
INSERT package011(item, mrp, sp)  
VALUES ('book1', 250, 240);

INSERT package011(item, mrp, sp)  
VALUES ('book2', 350, 320);

INSERT package011(item, mrp, sp)  
VALUES ('book3', 400, 350);
```

**读取数据–**

```sql
SELECT AVG(mrp-sp) FROM package011;
```

**输出:**

```sql
30
```

**应用:**

该函数用于求指定表达式的平均值。