# MySQL 中的数学函数

> 原文：[https://www.geeksforgeeks.org/mathematical-functions-in-mysql/](https://www.geeksforgeeks.org/mathematical-functions-in-mysql/)

[`SQL`](https://www.geeksforgeeks.org/sql-tutorial/) 代表‘结构化查询语言’。顾名思义，数据以行和列的形式以结构化格式存储。使用 `SQL` 语言，我们可以存储、检索和操作存储在 `MySQL` 数据库中的数据。

有时，数据库表包含数千个条目。例如，包含数千名员工的工资信息的表。现在假设，公司经理想计算员工的平均工资，或者想计算他支付给员工的工资总额。对他来说，手动完成这项工作将是非常忙乱的，因为这将非常耗费时间和精力。因此，在这种情况下，`MySQL` 中有一些数学函数可以使用。

为了方便起见，我们将把表名看作“雇员”，把包含雇员工资信息的列名看作整篇文章的“工资”。

在本文中，我们将研究 5 个这样的函数：

```sql
1. COUNT()
2. AVG()
3. SUM()
4. MIN()
5. MAX() 
```

让我们一个接一个地看看它们。

## 1. `COUNT()` 函数

`COUNT()` 函数返回匹配指定条件的行数。

例如，经理想要找出工资大于或等于每月 40,000 卢比的员工数量。使用 `COUNT()` 函数，他可以创建一个通用的 `MySQL` 查询来获取所需数据。

```sql
SELECT COUNT(salary)
FROM employees
WHERE salary >= 40000;
```

这将获取他所有工资等于或高于 40,000 卢比的员工的信息。

## 2. `AVG()` 函数

`AVG()` 函数将帮助经理确定所有员工的平均工资。
输出将以 `int` 的形式返回。

```sql
SELECT AVG(salary)
FROM employees;
```

## 3. `SUM()` 函数

`SUM()` 函数返回数值列的总和。
这将有助于经理了解他发放员工工资的总支出。

```sql
SELECT SUM(Price)
FROM Products;
```

## 4. `MAX()` 函数

顾名思义，`MAX()` 函数返回所选列的最大值。这意味着经理可以使用此功能来查找其公司中领取最高工资的员工。
该功能的工作代码为：

```sql
SELECT MAX(column_name)
FROM table_name;
```

## 5. `MIN()` 函数

`MIN()` 函数返回所选列的最小值。该功能可以查找从公司领取最低工资的员工的信息。
该功能的工作代码为：

```sql
SELECT MIN(column_name)
FROM table_name;
```