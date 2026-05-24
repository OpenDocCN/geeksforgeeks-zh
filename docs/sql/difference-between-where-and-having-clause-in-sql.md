# SQL 中 Where 子句和 Having 子句的区别

> 原文:[https://www . geesforgeks . org/where-and-having-in-SQL 子句的区别/](https://www.geeksforgeeks.org/difference-between-where-and-having-clause-in-sql/)

**1。WHERE 子句:**
WHERE 子句用于从表中筛选记录，或者在连接多个表时使用。只有满足 WHERE 子句中指定条件的记录才会被提取。它可以与 SELECT、UPDATE、DELETE 语句一起使用。

让我们考虑下表“学生”

```sql
Roll_no       S_Name      Age

1                a             17

2                b             20

3                c             21

4                d             18

5                e             20

6                f             17

7                g             21

8                h             17 
```

考虑查询:

```sql
SELECT S_Name, Age FROM Student 
WHERE Age >=18
```

上述查询的输出为:

```sql
 S_Name      Age

b             20             

c             21             

d             18             

e             20             

g             21             
```

**2。HAVING 子句:**
HAVING 子句用于根据 HAVING 子句中的给定条件从组中筛选记录。那些满足给定条件的组将出现在最终结果中。HAVING 子句只能与 SELECT 语句一起使用
。

让我们考虑上面提到的学生表，并在上面应用有子句:

```sql
SELECT Age, COUNT(Roll_No) AS No_of_Students 
FROM Student GROUP BY Age
HAVING COUNT(Roll_No) > 1 
```

上述查询的输出为:

```sql
Age     No_of_Students

17              3

20              2

21              1 
```

**SQL 中 Where 子句和 Having 子句的区别:**

<figure class="table">

| SR number | WHERE clause | 拥有子句 |
| --- | --- | --- |
| 1。 | WHERE clause is used to filter records from the table according to specified conditions. | The HAVING clause is used to filter records from a group according to specified criteria. |
| 2。 | The WHERE clause can be used without the GROUP BY clause | HAVING clause cannot be used without GROUP BY clause. |
| 3。 | WHERE clause is implemented in row operation | HAVING clause implemented in column operation |
| 4。 | WHERE clause cannot contain aggregate function | HAVING clause can contain aggregate function. |
| 5。 | The WHERE clause can be used with SELECT, UPDATE and DELETE statements. | HAVING clause can only be used with SELECT statement. |
| 6。 | The WHERE clause is used before the GROUP BY clause | HAVING clause is used after GROUP BY clause. |
| 7。 | The WHERE clause is used with single-line functions such as UPPER and LOWER. | HAVING clause is used with multi-line functions such as SUM and COUNT. |

</figure>