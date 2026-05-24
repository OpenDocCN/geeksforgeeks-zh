# 使用极限和偏移

## 查找列中第 n 个最大值的 SQL 查询

> 原文: [https://www.geeksforgeeks.org/sql-query-to-find-the-nth-largest-value-in-a-column-using-limit-and-offset/](https://www.geeksforgeeks.org/sql-query-to-find-the-nth-largest-value-in-a-column-using-limit-and-offset/)

### 先决条件
[如何从表中找到第 n 个最高工资](https://www.geeksforgeeks.org/find-nth-highest-salary-table/)

**问题陈述:** 使用 [`LIMIT`](https://www.geeksforgeeks.org/sql-limit-clause/) 和 [`OFFSET`](https://www.geeksforgeeks.org/sql-offset-fetch-clause/) 编写一个 SQL 查询从列中找到第 n 个最大值。

### 示例-1

**表格–**账单

| 公寓号 | 电费账单 |
| --- | --- |
| 101 | 1000 |
| 102 | 1500 |
| 103 | 1300 |
| 201 | 2300 |
| 202 | 6700 |
| 203 | 7500 |
| 204 | 1300 |
| 301 | 2300 |

上表列出了一套公寓所有公寓的电费账单。你必须找到表格中第 n 大的电费账单。

```sql
SELECT DISTINCT `ElectricityBill` AS `NthHighestElectricityBill`
FROM `Bills`
ORDER BY `ElectricityBill` DESC
LIMIT 1 
OFFSET `n-1`;
```

这里 `n` 应该是一个整数，其值必须大于零。

**解释:**
在上面的查询中，我们使用 [`Order By` 子句](https://www.geeksforgeeks.org/sql-order-by/)并通过仅选择不同的值，以降序对电费列的值进行排序。在按降序排序之后，我们必须从顶部找到第 N 个值，因此我们使用了 `OFFSET n-1`，它从列表中删除了顶部的 `n-1` 个值，现在从剩余的列表中，我们必须只选择它的顶部元素，为此我们使用了 `LIMIT 1`。

如果我们想找到第三高的电费账单，查询将是–

```sql
SELECT DISTINCT `ElectricityBill` AS `3rdHighestElectricityBill`
FROM `Bills`
ORDER BY `ElectricityBill` DESC
LIMIT 1
OFFSET 2;
```

上述查询的结果将是–

| 3rdHighestElectricityBill |
| --- |
| 2300 |

### 示例-2

**表–**员工工资

| Employee ID | SalaryInThousands |
| --- | --- |
| 1a2b | 259 |
| 3c4d | 316 |
| 5e6f | 259 |
| 7g8h | 412 |
| 9i0j | 128 |

上表是在小公司工作的员工的工资。找到收入第四高的员工 id。

```sql
SELECT `EmployeeID` AS `4thHighestEarningEmployee` 
FROM `EmployeeSalary`
ORDER BY `SalaryInThousands` DESC
LIMIT 1 
OFFSET 3;
```

**解释:**
这里不使用 `distinct`，因为我们需要收入在所有员工中排名第四的员工(即 316k 而不是 259k)。

上述查询的结果将是–

| 4thHighestEarningEmployee |
| --- |
| 3c4d |