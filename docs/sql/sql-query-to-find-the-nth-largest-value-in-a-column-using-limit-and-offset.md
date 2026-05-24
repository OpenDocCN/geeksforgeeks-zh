# 使用极限和偏移

查找列中第 n 个最大值的 SQL 查询

> 原文:[https://www . geesforgeks . org/SQL-查询查找第 n 个最大列值-使用限制和偏移量/](https://www.geeksforgeeks.org/sql-query-to-find-the-nth-largest-value-in-a-column-using-limit-and-offset/)

先决条件–[如何从表中找到第 n 个最高工资](https://www.geeksforgeeks.org/find-nth-highest-salary-table/)
**问题陈述:**使用 [LIMIT](https://www.geeksforgeeks.org/sql-limit-clause/) 和 [OFFSET](https://www.geeksforgeeks.org/sql-offset-fetch-clause/) 编写一个 SQL 查询从列中找到第 n 个最大值。

**示例-1 :**

**表格–**账单

<figure class="table">

| 公寓号。 | 电费账单 |
| --- | --- |
| One hundred and one | One thousand |
| One hundred and two | One thousand five hundred |
| One hundred and three | One thousand three hundred |
| Two hundred and one | Two thousand three hundred |
| Two hundred and two | Six thousand seven hundred |
| Two hundred and three | Seven thousand five hundred |
| Two hundred and four | One thousand three hundred |
| Three hundred and one | Two thousand three hundred |

</figure>

上表列出了一套公寓所有公寓的电费账单。你必须找到表格中第 n 大的电费账单。

```sql
SELECT DISTINCT ElectricityBill AS NthHighestElectricityBill
FROM Bills
ORDER BY ElectricityBill DESC
LIMIT 1 
OFFSET n-1;
```

这里 n 应该是一个整数，其值必须大于零。

**解释:**
在上面的查询中，我们使用 [Order By 子句](https://www.geeksforgeeks.org/sql-order-by/)并通过仅选择不同的值，以降序对电费列的值进行排序。在按降序排序之后，我们必须从顶部找到第 N 个值，因此我们使用了 OFFSET n-1，它从列表中删除了顶部的 n-1 个值，现在从剩余的列表中，我们必须只选择它的顶部元素，为此我们使用了 LIMIT 1。

如果我们想找到第三高的电费账单，查询将是–

```sql
SELECT DISTINCT ElectricityBill AS 3rdHighestElectricityBill
FROM Bills
ORDER BY ElectricityBill DESC
LIMIT 1
OFFSET 2;
```

上述查询的结果将是–

<figure class="table">

| 3 高成本电力法案 |
| --- |
| Two thousand three hundred |

</figure>

**示例-2 :**

**表–**员工工资

| Employee ID | [Salary residence] |
| --- | --- |
| 【T134】 |

上表是在小公司工作的员工的工资。找到收入第四高的员工 id。

```sql
SELECT EmployeeID AS 4thHighestEarningEmployee 
FROM EmployeeSalary
ORDER BY SalaryInThousands DESC
LIMIT 1 
OFFSET 3;
```

**解释:**
这里不使用 distinct，因为我们需要收入在所有员工中排名第四的员工(即 316k 而不是 259k)。

上述查询的结果将是–

<figure class="table">

| 第四高等教育雇主 |
| --- |
| 2a 748 |

</figure>