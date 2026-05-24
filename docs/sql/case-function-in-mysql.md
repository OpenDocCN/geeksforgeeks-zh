# MySQL 中的 CASE()函数

> 原文:[https://www.geeksforgeeks.org/case-function-in-mysql/](https://www.geeksforgeeks.org/case-function-in-mysql/)

[MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中的 CASE()函数用于在任何条件满足给定语句时通过传递条件来查找值，否则它会在其他部分返回该语句。但是，当满足某个条件时，它会停止进一步读取并返回输出。

**特征:**

*   If the stated conditions are not true, this function returns the statement of the else part.
*   If none of the conditions are true and there are no other parts, the function returns a null value.
*   This function is an advanced function.
*   This function accepts two parameters, namely condition and result.

**语法:**

```sql
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    WHEN conditionN THEN resultN
    ELSE result
END;
```

**参数:**

该方法接受如下给出的两个参数:

*   **Condition 1, Condition 2, … Condition N:** The specified conditions are determined according to the order in which they are stated.
*   **Result 1, Result 2, … Result n:** If the conditions are met, the specified output will be returned.

**返回:**只要任何条件满足给定的语句，它就通过传递条件来返回值，否则它在 else 部分返回语句。如果没有满足任何条件，也没有其他部分，则返回空值。

**示例 1:** 使用 CASE()函数并获取输出。

```sql
CREATE TABLE float01001
(  
user_id int NOT NULL AUTO_INCREMENT,
float_val float,
PRIMARY KEY(user_id)
);
INSERT float01001(float_val)  
VALUES (1.9);

INSERT float01001(float_val)  
VALUES (1.1);

INSERT float01001(float_val)  
VALUES (3.9);

INSERT float01001(float_val)  
VALUES (5.0);

INSERT float01001(float_val)  
VALUES (10.9);

SELECT float_val,
CASE
    WHEN float_val > 5 THEN "The value is greater than 5"
    WHEN float_val = 5 THEN "The value is 5"
    ELSE "The value is under 5"
END as float_txt
FROM float01001;
```

**输出:**

```sql
float_val  | float_txt
-------------------------------------------
  1.9      | The value is under 5
------------------------------------------- 
  1.1      | The value is under 5
-------------------------------------------
  3.9      | The value is under 5
-------------------------------------------
  5        | The value is 5
-------------------------------------------
  10.9     | The value is greater than 5
```

**例 2:**

使用 CASE()函数，检查所述浮点值的长度是否大于、小于或等于 4。

```sql
CREATE TABLE float01001
(  
user_id int NOT NULL AUTO_INCREMENT,
float_val float,
PRIMARY KEY(user_id)
);
INSERT float01001(float_val)  
VALUES (9.0);

INSERT float01001(float_val)  
VALUES (7.7);

INSERT float01001(float_val)  
VALUES (30.91);

INSERT float01001(float_val)  
VALUES (8.0);

INSERT float01001(float_val)  
VALUES (10.9);

SELECT float_val,
CASE
    WHEN LENGTH(float_val) > 4 THEN "The length is greater than 4"
    WHEN LENGTH(float_val) = 4 THEN "The length is 4"
    ELSE "The length is less than 4"
END as float_txt
FROM float01001;
```

**输出:**

```sql
float_val  | float_txt
-------------------------------------------
 9         | The length is less than 4
-------------------------------------------
 7.7       | The length is less than 4
-------------------------------------------
 30.91     | The length is greater than 4
-------------------------------------------
 8.0       | The length is less than 4
-------------------------------------------
 10.9      | The length is 4
```

**例 3:**

使用 CASE()函数，检查所述项目的物料需求计划是否大于 400。

```sql
CREATE TABLE package099
(  
user_id int NOT NULL AUTO_INCREMENT,
item VARCHAR(10),
mrp int,
PRIMARY KEY(user_id)
);
INSERT package099(item, mrp)  
VALUES ('book1', 350);

INSERT package099(item, mrp)  
VALUES ('book2', 500);

SELECT mrp,
CASE
    WHEN mrp > 400 THEN "Buy this item"
    ELSE "Don't buy this item"
END as txt
FROM package099;
```

**输出:**

```sql
mrp  | txt
------------------------------
 350 |  Don't buy this item
------------------------------
 500 |  Buy this item
```

**例 4:**

使用 CASE()函数并检查损益。

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
VALUES ('book1', 250, 255);

INSERT package72(item, mrp, sp)  
VALUES ('book2', 350, 370);

INSERT package72(item, mrp, sp)  
VALUES ('book3', 400, 350);

SELECT mrp,sp,
CASE
    WHEN sp > mrp THEN "Profit"
    ELSE "Loss"
END as PL
FROM package72;
```

**输出:**

```sql
mrp  | sp  | PL
-----------------------
 250 | 255 | Profit
-----------------------
 350 | 370 | Profit
 ----------------------
 400 | 350 | Loss
```

**应用:**该函数用于在任何条件满足给定语句时通过传递条件来查找值，否则它会在其他部分返回该语句。