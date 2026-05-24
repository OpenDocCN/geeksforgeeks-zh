# 听起来像是 MySQL 中的函数

> 原文:[https://www . geesforgeks . org/sounds-like-function-in-MySQL/](https://www.geeksforgeeks.org/sounds-like-function-in-mysql/)

**Soundex LIKE:**
MySQL 中的这个函数用来比较给定的两个字符串表达式的 Soundex 代码。它用作 SOUNDEX(exp 1)= SOUNDEX(exp 2)来检索听起来相似的字符串。

**语法:**

```sql
expr1 SOUNDS LIKE expr2

```

**参数:**
它接受上面提到的和下面描述的两个参数。

*   **表达式 1–**我们要比较的第一个字符串。
*   **表达式 2–**我们要比较的第二个字符串。

**返回:**
比较两个字符串值的 Soundex 代码，返回输出。

**示例-1 :**
使用 SOUNDS LIKE 函数比较相似的两个给定字符串。

```sql
SELECT 'geeks' SOUNDS LIKE 'geeks' 
as Result;
```

**输出:**

| **结果** |
| --- |
| one |

**示例-2 :**
使用 SOUNDS LIKE 函数比较相似的两个给定字符串。

```sql
SELECT 'geeks' SOUNDS LIKE 'for' 
as Result;
```

**输出:**

| **结果** |
| --- |
|     0 |

**示例-3 :**
以下示例显示返回所有包含员工姓名的行，该员工姓名的名字听起来像“Sayan”。

```sql
CREATE TABLE Employee
(
Employee_id INT AUTO_INCREMENT,  
First_name VARCHAR(100) NOT NULL,
Last_name VARCHAR(100) NOT NULL,
Joining_Date DATE NOT NULL,
PRIMARY KEY(Employee_id )
);
```

**在员工表中插入一些数据:**

```sql
INSERT INTO Employee
(First_name ,Last_name , Joining_Date )
VALUES
('Sayantan', 'Majumdar', '2000-01-11'),
('Anushka', 'Samanta', '2002-11-10' ),
('Sayan', 'Sharma', '2005-06-11' ),
('Shayari', 'Das', '2008-01-21' ),
('Sayani', 'Jain', '2008-02-01' ),
('Tapan', 'Samanta', '2010-01-11' ),
('Deepak', 'Sharma', '2014-12-01'  ),
('Ankana', 'Jana', '2018-08-17'),
('Shreya', 'Ghosh', '2020-09-10') ;

```

因此，员工表如下。

```sql
select * from Employee ;
```

**输出:**

| **员工 _id** | **名** | **姓氏** | **加入 _ 日期** |
| --- | --- | --- | --- |
| one | 萨彦坦 | Majumdar | 2000-01-11 |
| Two | 阿努什卡 | 萨曼塔 | 2002-11-10 |
| three | Sayan | 夏尔马 | 2005-06-11 |
| four | 沙雅里 | 这是什么 | 2008-01-21 |
| five | Sayani | 耆那教教徒 | 2008-02-01 |
| six | 塔潘 | 萨曼塔 | 2010-01-11 |
| seven | 迪帕克（男子名） | 夏尔马 | 2014-12-01 |
| eight | 安卡拉 | 陈娟儿 | 2018-08-17 |
| nine | 施莱 | 幽灵 | 2020-09-10 |

现在，我们要检查那些名字听起来像“sayan”的员工。

```sql
SELECT * FROM Employee 
WHERE First_name SOUNDS LIKE 'Sayan' ;
```

**输出:**

| **员工 _id** | **名** | **姓氏** | **加入 _ 日期** |
| --- | --- | --- | --- |
| three | Sayan | 夏尔马 | 2005-06-11 |
| five | Sayani | 耆那教教徒 | 2008-02-01 |