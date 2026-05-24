# 如何在 SQL 中左连接多个表

> 原文: [https://www.geeksforgeeks.org/how-to-left-join-multiple-tables-in-sql/](https://www.geeksforgeeks.org/how-to-left-join-multiple-tables-in-sql/)

左连接是在 SQL 中编写查询时使用的关键字之一。在 SQL 中，我们通常使用连接，通过从通常具有匹配记录的两个表中取出像行或记录或元组这样的公共数据来形成一个新表。

这里，当涉及到 SQL 中的左连接时，它只返回左表中的所有记录或元组或行，并且只返回右表中匹配的那些记录。

## 左连接语法

```sql
SELECT column names
FROM table1
LEFT JOIN table2
ON table1.matching_column = table2.matching_column;
```

**注意:** 例如，如果您有一个 10 行的左表，在对两个表应用联接操作后，保证至少有 10 行。

## 考虑两张表

### 1. 员工(左表)

| Emp_Id | 名字 | 姓氏 | gender | age | 日期_of_join |
| --- | --- | --- | --- | --- | --- |
| one | Plane | Tanru | M | Thirty-four | four |
| two | Vasili | Vasili | M | Thirty | 2006-02-31 |
| three | Clara | F | F | Thirty-four | 2008-08-26 |
| four | simple | Vassar | M | Twenty-eight | 2010-05-12 |
| five | Hadik | Pabu | M | Forty-five | 2015-07-23 |

### 2. 项目(右表)

| 身份证明（identification） | date | Project_No | Emp_id | 工作小时数 |
| --- | --- | --- | --- | --- |
| one | 2005-03-15 | One hundred and forty-seven | three | 162 |
| two | 2006-04-10 | One hundred and forty-eight | three | 192 |
| three | 2007-05-20 | One hundred and forty-nine | one | 175 |

为了连接这两个表并获得公共信息，我们需要使用以下查询

```sql
SELECT E.Emp_id, E.First_Name, E.Last_Name, E.Gender, E.age, E.Date_of_join,    
       P.date AS Project_Assigned_date, P.No_of_hours_worked AS hours_worked
FROM Employee E
LEFT JOIN Projects P
ON E.Emp_id = P.Emp_id
GROUP BY E.Emp_id;
```

执行查询后，得到的表将如:

| Emp_Id | Name_name | Last name_name | gender | age | 日期_of_join | 项目_分配日期 | 小时_成功 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| one | Plane | Tanru | M | Thirty-four | four | 2005-03-16 | One hundred and ninety-two |
| two | Vasili | Vasili | M | Thirty | 2006-02-31 | NULL | NULL |
| three | Clara | F | F | Thirty-four | 2008-08-26 | 2005-03-17 | 162 |
| four | simple | Vassar | M | Twenty-eight | 2010-05-12 | NULL | NULL |
| five | Hadik | Pabu | M | Forty-five | 2015-07-23 | NULL | NULL |

*   获得表格后，您可以看到，未分配给项目的 `Emp_id` 的“项目分配日期”变为空，并且“工作小时数”也变为空，因为员工没有分配任何工作。
*   这里左连接的意思是，基于上面的表，它从匹配的两个表行中获取数据，并且它还返回表 2 中不存在的行的值作为空值，因为我们需要考虑左表的所有数据。

## 一个查询中的多个左连接

有时您需要左连接两个以上的表来获取特定分析所需的数据。幸运的是，`LEFT JOIN` 关键字可以与 SQL 中的 `MULTIPLE TABLES` 一起使用。

### 考虑一个名为 Salary 的表

| 身份证明（identification） | Emp_id | 薪资公司 | 日期 |
| --- | --- | --- | --- |
| one | one | 50000 | 2015-01-01 |
| two | two | 55000 | 2016-02-01 |
| three | three | 60000 | 2017-03-01 |

这里，我们将这些表中的数据合并为员工、项目和薪资。

为此，查询需要按照以下格式编写:

```sql
SELECT E.Emp_id, E.First_Name, E.Last_Name, E.Gender, E.age, E.Date_of_join,  
   P.No_of_hours_worked AS hours_worked, S.Salary_inc AS Salary_Increment
FROM Employee E
LEFT JOIN Projects P
ON E.Emp_id = P.Emp_id
LEFT JOIN Salary S
ON E.Emp_id = S.Emp_id;
```

而生成的表看起来像是在**多次左联接**之后:

| Emp_id | 名字 | 姓氏 | gender | age | 日期_of_join | Working time_worked | Salary_increment |
| --- | --- | --- | --- | --- | --- | --- | --- |
| one | Plane | Tanru | M | Thirty-four | four | 192 | 50000 |
| two | Vasili | Vasili | M | Thirty | 2006-02-31 | NULL | 55000 |
| three | Clara | F | F | Thirty-four | 2008-08-26 | 162 | 60000 |
| four | simple | Vassar | M | Twenty-eight | 2010-05-12 | NULL | NULL |
| five | Hadik | Pabu | M | Forty-five | 2015-07-23 | NULL | NULL |

因此，您可以看到，我们多次使用左连接将三个表中的数据合并到一个表中。

### 再考虑一个名为 Experience 的表

| 身份证明（identification） | Emp_name | 经验 |
| --- | --- | --- |
| one | Plane | five |
| Two | Santosh | four |
| three | Clara | three |

在这里，我们结合了这些表格中的数据员工，项目和经验。

为此，查询需要按照以下格式编写:

```sql
SELECT E.Emp_id, E.First_Name, E.Last_Name, P.date AS Project_Assigned_date, 
E1.Experience AS EXP
FROM Employee E
LEFT JOIN Projects P
ON E.Emp_id = P.Emp_id
LEFT JOIN Experience E1
ON E.Emp_id = E1.id;
```

而生成的表看起来像是经过**多次左连接:**

| Emp_id | 名字 | 姓氏 | 项目_分配_日期 | EXP |
| --- | --- | --- | --- | --- |
| one | 普拉内 | 坦纳鲁 | 2005-03-17 | five |
| two | Vasili | Vasili | NULL | four |
| three | Clara | F | 2005-03-17 | three |
| four | simple | Vassar | NULL | NULL |
| five | Hadik | Pabu | NULL | NULL |

如您所见，SQL 中的 `LEFT JOIN` 可以用于多个表。