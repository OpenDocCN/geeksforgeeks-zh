# MySQL 中的 TIMESTAMPDIFF()函数

> 原文:[https://www . geesforgeks . org/timestampdiff-function-in-MySQL/](https://www.geeksforgeeks.org/timestampdiff-function-in-mysql/)

**TIMESTAMPDIFF() :**

MySQL 中的这个函数用来在从另一个表达式中减去一个 DateTime 表达式后返回值。

**语法:**

```sql
TIMESTAMPDIFF(unit,expr1,expr2)
```

**参数:**

它将接受三个参数。

*   **单位–**
    表示结果的单位。它可以是下列之一。
    微秒、秒、分、小时、日、周、月、季度、年

*   **表达式 1–**
    第一个日期或日期时间表达式。

*   **表达式 2–**
    第二个日期或日期时间表达式。

**返回:**

它返回减法后的日期时间表达式。

**例 1 :**

获取两个指定时间值之间的差值，其中时间以 YYYY-MM-DD HH-MM-SS 格式指定。这里 expr2 大于 expr1，所以返回值为正。

```sql
SELECT TIMESTAMPDIFF(SECOND, '2010-01-01 10:10:20', '2010-01-01 10:45:59') AS SECONDDIFFERENCE;
```

**输出:**

<figure class="table">

| Second difference |
| --- |
| Two thousand one hundred and thirty-nine |

</figure>

**例 2:**

获取两个指定时间值之间的差值，其中时间以 YYYY-MM-DD HH-MM-SS 格式指定。这里 expr2 小于 expr1，所以返回值为负。

```sql
SELECT TIMESTAMPDIFF(SECOND, '2010-01-01 10:10:20', '2010-01-01 09:45:59') AS SECONDDIFFERENCE;
```

**输出:**

<figure class="table">

| Second difference |
| --- |
| -1461 |

</figure>

**例 3:**

当日期以 YYYY-MM-DD 格式指定时，获取月份中两个指定日期值之间的差异。

```sql
SELECT TIMESTAMPDIFF(MONTH, '2019-08-01', '2020-11-01') AS MONTHDIFFERENCE;
```

**输出:**

<figure class="table">

| 蒙特迪夫会议 |
| --- |
| Fifteen |

</figure>

**例 4:**

使用 TIMESTAMPDIFF 函数计算员工的总工作经验。

**创建员工表–**

```sql
CREATE TABLE Employee(
    id INT AUTO_INCREMENT PRIMARY KEY,
    Full_Name VARCHAR(50) NOT NULL,
    Joining_Date DATE NOT NULL
);
```

**将值插入表格–**

```sql
INSERT INTO Employee(Full_Name , Joining_Date )
VALUES('Riya Jana', '2000-01-01'),
      ('Sayan Ghosh', '2005-09-26'),
      ('Rinki Sharma', '2014-08-12'),
      ('Aniket Singh', '2019-11-05');
```

现在，我们将使用 TIMESTAMPDIFF 来计算每个员工在一年中的工作经历。

```sql
SELECT 
    id,
    Full_Name,
    Joining_Date ,
    TIMESTAMPDIFF(YEAR, Joining_Date,'2020-11-26') AS WorkExperience
FROM
    Employee ;
```

**输出:**

<figure class="table">工作经验

| 【id】 | [Full name] | 【加入 _ 日期】 |
| --- | --- | --- |

</figure>