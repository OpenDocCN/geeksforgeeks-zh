# MySQL 中的 LTRIM()函数

> 原文:[https://www.geeksforgeeks.org/ltrim-function-in-mysql/](https://www.geeksforgeeks.org/ltrim-function-in-mysql/)

**LTRIM():**
MySQL 中的这个函数用于删除字符串中的前导空格。

**语法:**

```sql
LTRIM(str)
```

**参数:**
它接受一个参数，如上所述，如下所述。

*   **str–**我们要从中删除前导空格的字符串。

**返回:**
截断所有前导空格后返回字符串。

**示例-1 :**
使用 LTRIM 函数移除给定字符串的所有前导空格。

```sql
SELECT '    geeksforgeeks'  As OriginalString,
LTRIM ('    geeksforgeeks')  AS LeftTrimmedString;
```

**输出:**

| **原串** | **笔译摘要** |
| --- | --- |
| 极客们 | 极客们 |

**示例-2 :**
使用 LTRIM 函数移除给定字符串的所有前导空格。

```sql
SELECT '    MySQL' AS String, 
RTRIM ('MySQL')  AS Tstring;
```

**输出:**

| **弦** | **星环** |
| --- | --- |
| 关系型数据库 | 关系型数据库 |

**示例-3 :**
LTRIM 函数也可以用来删除列数据的所有前导空格。为了演示，创建一个名为 Employee 的表。

```sql
CREATE TABLE Employee
(
 Employee_id INT AUTO_INCREMENT,  
 Employee_name VARCHAR(100) NOT NULL,
 Joining_Date DATE NOT NULL,
 PRIMARY KEY(Employee_id )
);
```

**在员工表中插入一些数据:**

```sql
INSERT INTO Employee
(Employee_name, Joining_Date )
VALUES
 ('     Ananya Majumdar', '2000-01-11'),
 ('   Anushka Samanta', '2002-11-10' ),
 ('   Aniket Sharma ', '2005-06-11' ),
 ('   Anik Das', '2008-01-21'  ),
 ('  Riya Jain', '2008-02-01' ),
 ('    Tapan Samanta', '2010-01-11' ),
 ('   Deepak Sharma', '2014-12-01'  ),
 ('   Ankana Jana', '2018-08-17'),
 ('  Shreya Ghosh', '2020-09-10') ;
```

因此，员工表如下。

```sql
select * from Employee ;
```

**输出:**

| **员工 _id** | **员工 _ 姓名** | **加入 _ 日期** |
| --- | --- | --- |
| one | Ananya Majumdar | 2000-01-11 |
| Two | 阿努什卡·萨曼塔 | 2002-11-10 |
| three | 阿尼克·夏尔马 | 2005-06-11 |
| four | 大哥！大哥 | 2008-01-21 |
| five | 里亚耆那教 | 2008-02-01 |
| six | 塔潘·萨曼塔 | 2010-01-11 |
| seven | 迪帕克·夏尔马 | 2014-12-01 |
| eight | 约翰娜的鸭子 | 2018-08-17 |
| nine | Shreya Ghosh | 2020-09-10 |

现在，我们将从 Employee_name 列中删除所有前导空格。

```sql
 SELECT  
 Employee_id,  Employee_name,
 LTRIM( Employee_name) AS  TrimmedEname  
 FROM  Employee ;
```

**输出:**

| **员工 _id** | **员工 _ 姓名** | 修整名称 |
| --- | --- | --- |
| one | Ananya Majumdar | Ananya Majumdar |
| Two | 阿努什卡·萨曼塔 | 阿努什卡·萨曼塔 |
| three | 阿尼克·夏尔马 | 阿尼克·夏尔马 |
| four | 大哥！大哥 | 大哥！大哥 |
| five | 里亚耆那教 | 里亚耆那教 |
| six | 塔潘·萨曼塔 | 塔潘·萨曼塔 |
| seven | 迪帕克·夏尔马 | 迪帕克·夏尔马 |
| eight | 约翰娜的鸭子 | 约翰娜的鸭子 |
| nine | Shreya Ghosh | Shreya Ghosh |