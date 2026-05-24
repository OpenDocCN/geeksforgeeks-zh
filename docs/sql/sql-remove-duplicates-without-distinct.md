# SQL |删除无差异的重复项

> 原文:[https://www . geesforgeks . org/SQL-remove-duplicates-不带-distinct/](https://www.geeksforgeeks.org/sql-remove-duplicates-without-distinct/)

DISTINCT 在某些情况下很有用，但它有一个缺点，那就是它会增加查询引擎执行排序的负载(因为它需要将结果集与自身进行比较来删除重复项)

以下是替代解决方案:

**1。使用[行号](https://docs.microsoft.com/en-us/sql/t-sql/functions/row-number-transact-sql?view=sql-server-2017)删除重复项。**

```sql
WITH CTE (Col1, Col2, Col3, DuplicateCount)
AS
(
  SELECT Col1, Col2, Col3,
  ROW_NUMBER() OVER(PARTITION BY Col1, Col2,
       Col3 ORDER BY Col1) AS DuplicateCount
  FROM MyTable
) SELECT * from CTE Where DuplicateCount = 1
```

**2。使用自连接**
表删除重复项

```sql
emp_name   emp_address  sex  matial_status  
uuuu       eee          m    s
iiii       iii          f    s
uuuu       eee          m    s
```

```sql
SELECT emp_name, emp_address, sex, marital_status
from YourTable a
WHERE NOT EXISTS (select 1 
         from YourTable b
         where b.emp_name = a.emp_name and
               b.emp_address = a.emp_address and
               b.sex = a.sex and
               b.create_date >= a.create_date)
```

**3。使用**
分组删除重复项的想法是根据输出中要选择的所有列进行分组。例如，如果我们希望打印“名字、姓氏和手机号”的唯一值，我们可以简单地将这三个值分组。

```sql
SELECT FirstName, LastName, MobileNo
FROM  CUSTOMER
GROUP BY FirstName, LastName, MobileNo;

```