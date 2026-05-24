# SQL–逻辑运算符

> 原文:[https://www.geeksforgeeks.org/sql-logical-operators/](https://www.geeksforgeeks.org/sql-logical-operators/)

SQL 逻辑运算符用于测试条件的真实性。像[比较](https://www.geeksforgeeks.org/sql-operators/)运算符这样的逻辑运算符返回的布尔值为**真**、**假**、或未知。

下面给出了 SQL 中可用的逻辑运算符列表。

<figure class="table">

| **Operator** | **means** |
| [**和**T3】](https://www.geeksforgeeks.org/sql-and-and-or-operators/) | TRUE if both Boolean expressions are TRUE. |
| [**在**](https://www.geeksforgeeks.org/sql-between-in-operator/) | True if the operand is equal to one of the expression lists. |
| [**不是**](https://www.geeksforgeeks.org/sql-not-operator/) | Inverts the value of any other Boolean operator. |
| [**或**T3】](https://www.geeksforgeeks.org/sql-and-and-or-operators/) | If any Boolean expression is true, it is true. |
| [**LIKE**](https://www.geeksforgeeks.org/sql-like/) | TRUE if the operand matches a pattern. |
| [](https://www.geeksforgeeks.org/sql-between-in-operator/) | True if the operand is in a range. |
| [**ALL**](https://www.geeksforgeeks.org/sql-all-and-any/) | TRUE if a set of comparisons are all TRUE. |
| [**任意**](https://www.geeksforgeeks.org/sql-all-and-any/) | TRUE if any one of a set of comparisons is TRUE. |
| [**存在**](https://www.geeksforgeeks.org/sql-exists/) | TRUE if the subquery contains any rows. |
| [**有些**](https://www.geeksforgeeks.org/sql-some/) | TRUE if some comparisons in a set of comparisons are TRUE. |

</figure>

在下面的例子中，我们将看到这个逻辑运算符是如何工作的。

**步骤 1:** 创建数据库

为了创建数据库，我们需要使用 create 运算符。

**查询:**

```sql
CREATE DATABASE xstream_db;
```

![](img/562052f6fe1a116443aa93ce65e04167.png)

**步骤 2:** 创建员工表

在这一步中，我们将在 xstream_db 数据库中创建雇员表。

**查询:**

```sql
CREATE TABLE employee (emp_id INT, emp_name VARCHAR(255), 
                                  emp_city VARCHAR(255),
                                  emp_country VARCHAR(255),
                                  PRIMARY KEY (emp_id));
```

![](img/e7011903aa7696969c84353cd61da43d.png)

为了在数据库中插入数据，我们需要使用 insert 操作符。

**查询:**

```sql
INSERT INTO employee VALUES (101, 'Utkarsh Tripathi', 'Varanasi', 'India'),
                            (102, 'Abhinav Singh', 'Varanasi', 'India'), 
                            (103, 'Utkarsh Raghuvanshi', 'Varanasi', 'India'),
                            (104, 'Utkarsh Singh', 'Allahabad', 'India'),
                            (105, 'Sudhanshu Yadav', 'Allahabad', 'India'),
                            (106, 'Ashutosh Kumar', 'Patna', 'India');
```

![](img/8c0fca02a5a7f71b40cce4d0df4d8ee2.png)

**输出:**

![](img/fe49594fc24d236690d16d0134f34670.png)

下面给出的是逻辑运算符的一个例子。

### **和运算符**

**查询:**

```sql
SELECT * FROM employee WHERE emp_city = 'Allahabad' AND emp_country = 'India';
```

![](img/be3d66223d0245f8a35a07e69a8f3eb2.png)

**输出:**

![](img/9863bf2dab3096d9680bdf4a14caeb92.png)

### **输入操作符**

**查询:**

```sql
SELECT * FROM employee WHERE emp_city IN ('Allahabad', 'Patna');
```

![](img/f587416c2f5c420eca75e8b58a7097fd.png)

**输出:**

![](img/2d82302ae0e4a04127c9cfc4bddd10a0.png)

### **非操作员**

**查询:**

```sql
SELECT * FROM employee WHERE emp_city NOT LIKE 'A%';
```

![](img/48611ecf4efb0c299666e5225707994c.png)

**输出:**

![](img/74b2e07080798c4246c636b2695dd294.png)

### **或运算符**

**查询:**

```sql
SELECT * FROM employee WHERE emp_city = 'Varanasi' OR emp_country = 'India';
```

![](img/bd4b1924e2bd354f5bec4e5a15900fad.png)

**输出:**

![](img/5241e12def75238fb33be7a9e86cd4d0.png)

### **同操作员**

**查询:**

```sql
SELECT * FROM employee WHERE emp_city LIKE 'P%';
```

![](img/1f37a025efa4e2f70324562e91bbd0d0.png)

**输出:**

![](img/252d46271d28dfc6237f615b8f2c39c8.png)

### **操作员之间**

**查询:**

```sql
SELECT * FROM employee WHERE emp_id BETWEEN 101 AND 104;
```

![](img/6754c1931fbe9999eb7cb1ffde797129.png)

**输出:**

![](img/7f305e7dba03e40bd8620c771f75f3e0.png)

### **所有操作员**

**查询:**

```sql
SELECT * FROM employee WHERE emp_id = ALL 
                (SELECT emp_id FROM employee WHERE emp_city = 'Varanasi');
```

![](img/bb22ff7f551ec5fe1e544acec760ff45.png)

**输出:**

![](img/57a867cf4ff73693373b84aa06ff649b.png)

### **任何操作员**

**查询:**

```sql
SELECT * FROM employee WHERE emp_id = ANY
                (SELECT emp_id FROM employee WHERE emp_city = 'Varanasi');
```

![](img/442065887c1b5686370b3ec69e0bf7c3.png)

**输出:**

![](img/02e774bbdcf7972a2866f76c8f801ecc.png)

### **存在操作员**

**查询:**

```sql
SELECT emp_name FROM employee WHERE EXISTS
                (SELECT emp_id FROM employee WHERE emp_city = 'Patna');
```

![](img/7d7baad855b6f2c67ce6ee3b4d08c377.png)

**输出:**

![](img/8bd1df66a268e16c6b0152a71b2a04aa.png)

### **某些操作员**

**查询:**

```sql
SELECT * FROM employee WHERE emp_id < SOME 
                (SELECT emp_id FROM employee WHERE emp_city = 'Patna');
```

![](img/9655d67f654bfba94bb0127b4de49d16.png)

**输出:**

![](img/be0935d546f3c1a44ae98519b869347f.png)