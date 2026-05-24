# 如何在 SQL 中左连接多个表

> 原文:[https://www . geesforgeks . org/如何在 sql 中左连接多表/](https://www.geeksforgeeks.org/how-to-left-join-multiple-tables-in-sql/)

左连接是在 SQL 中编写查询时使用的关键字之一。在 SQL 中，我们通常使用连接，通过从通常具有匹配记录的两个表中取出像行或记录或元组这样的公共数据来形成一个新表。

这里，当涉及到 SQL 中的左连接时，它只返回左表中的所有记录或元组或行，并且只返回右表中匹配的那些记录。

**左连接语法:**

```sql
SELECT column names
FROM table1
LEFT JOIN table2
ON table1.matching_column = table2.matching_column;
```

**注意:**例如，如果您有一个 10 行的左表，在对两个表应用联接操作后，保证至少有 10 行。

**考虑两张表:**

**1。员工(左表) :**

<figure class="table">T21T30】45T60【2008-08-26】T61T63T66 简T70【FT72】30T74【2006-02-31】T75T77T80】哈迪

| Emp _ Id | 名字 | 姓氏 | gender | age | 日期 _ of _ join |
| --- | --- | --- | --- | --- | --- |
| one | Plane | Tanru | M | Thirty-four | four | 瓦西里！瓦西里 | five |

</figure>

**2。项目(右表):**

<figure class="table">

| 身份证明（identification） | date | Project _ No | Emp _ id | 工作小时数 |
| --- | --- | --- | --- | --- |
| one | 2005-03-15 | One hundred and forty-seven | three | 162【T22 |

</figure>

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

<figure class="table">T28 48T59T62 玛丽T68】34T70】2008-08-26

| Emp _ Id | Name _ name | Last name _ name | gender | age | 日期 _of_join | 项目 _ 分配日期 | 小时 _ 成功 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| one | Plane | 1999-07-10 | 2005-03-16 | One hundred and ninety-two | three | Clara | F |

</figure>

*   获得表格后，您可以看到，未分配给项目的 Emp_id 的“项目分配日期”变为空，并且“工作小时数”也变为空，因为员工没有分配任何工作。
*   这里左连接的意思是，基于上面的表，它从匹配的两个表行中获取数据，并且它还返回表 2 中不存在的行的值作为空值，因为我们需要考虑左表的所有数据。

**一个查询中的多个左连接:**
有时您需要左连接两个以上的表来获取特定分析所需的数据。幸运的是，LEFT JOIN 关键字可以与 SQL 中的 MULTIPLE TABLES 一起使用。

**考虑一个名为 Salary 的表:**

<figure class="table">T17T20】5T22】50000T24】2015-01-01T26T28】2T30

| 身份证明（identification） | Emp _ id | 薪资公司 | 日期 |
| --- | --- | --- | --- |
| one |

</figure>

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

<figure class="table">T26】1T52】48T54】1999-07-10T56】192T58】55000T60T62T64】玛丽 T66 克拉拉T70】34T72】2008-08-26

| Emp _ id | 名字 | 姓氏 | gender | age | 日期 _of_join | Working time _worked | Salary _ increment |
| --- | --- | --- | --- | --- | --- | --- | --- |
| M Plane |
| three | F |

</figure>

因此，您可以看到，我们多次使用左连接将三个表中的数据合并到一个表中。

**再考虑一个名为 Experience 的表:**

<figure class="table">T30

| 身份证明（identification） | Emp _ name | 经验 |
| --- | --- | --- |
| one | Plane | five |
| Two | Santosh | four |
| three |

</figure>

在这里，我们结合了这些表格中的数据员工，项目和经验。

为此，查询需要按照以下格式编写:

```sql
SELECT E.Emp_id, E.First_Name, E.Last_Name, P.date AS Project_Assigned_date, 
E1.Experience AS EXP
FROM Employee E
LEFT JOIN Projects
 P
ON E.Emp_id = P.Emp_id
LEFT JOIN Experience E1
ON E.Emp_id = E1.id;
```

而生成的表看起来像是经过**多次左连接:**

<figure class="table">T14】EXPT68】5

| Emp _ id | 名字 | 姓氏 | 项目 _ 分配 _ 日期 |
| --- | --- | --- | --- |
| one | 普拉内 | 坦纳鲁 | 2005-03-17【T27 | three |
| four | simple | Vassar | 【空】 | 【空】 |
| Hadik | Pabu | 【空】 | 【空】 |

</figure>

如您所见，SQL 中的 LEFT JOIN 可以用于多个表。