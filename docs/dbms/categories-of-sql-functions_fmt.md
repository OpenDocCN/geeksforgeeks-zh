# SQL 函数的类别

> 原文：[https://www.geeksforgeeks.org/categories-of-sql-functions/](https://www.geeksforgeeks.org/categories-of-sql-functions/)

**SQL 函数**被开发到甲骨文数据库中，可用于各种合适的 SQL 语句。SQL 中的函数和 Pl/SQL 中的用户定义函数是不同的。

在查询中，如果调用的 SQL 函数的参数数据类型不同于函数预期的数据类型，则 Oracle 会在执行 SQL 函数之前将参数数据类型转换为预期的数据类型，如果调用的函数参数为 null，则返回 null。

## 功能类别

```
1. Single_row_function
2. Aggregate_function
3. Analytic_function
4. Model_function
5. User_defined_function 
6. Scalar functions 
```

其中一些功能解释如下。

### 单行函数

单行函数是为查询的表或视图的每一行返回一个结果行的函数。该函数存在于选择列表、WHERE 子句、START WITH、CONNECT BY 子句和 HAVING 子句中。

- 数值函数
- 字符函数
- 数据挖掘函数
- 日期时间函数
- 转换函数
- 集合函数
- `XML` 函数

### 聚合函数

使用聚合函数时，它将基于行组而不是单行返回单行结果。聚合函数出现在选择列表以及 `ORDER BY` 和 `HAVING` 子句中。它们通常与 `GROUP BY` 子句和 `SELECT` 语句一起使用。

如果使用 `GROUP BY` 子句，则 Oracle 会将选择列表中的聚合函数应用于查询的表或视图中的所有行。

除分组和 `COUNT(*)` 之外的所有聚合函数都忽略空值。您也可以在聚合函数的参数中使用 `NVL` 函数来替换空值。

还可以嵌套聚合函数。例如：

```sql
SELECT AVG(MAX(salary)) 
FROM employees 
GROUP BY department_id;
```

最常用的聚合函数是 `AVG`、`COUNT`、`DENSE_RANK`、`MAX`、`MIN`、`RANK`、`SUM`。

### 分析函数

分析函数基于行组计算聚合值。分析函数与聚合函数的区别在于，它们为每个行组返回多行。行组被称为窗口，并由 `analytic_clause` 定义。

分析函数是查询中执行的最后一组操作，除了最后的 `ORDER BY` 子句。

- 分析子句
    - `QUERY PARTITION` 子句
    - `ORDER BY` 子句
    - 开窗子句

### 模型函数

在 `SELECT` 语句中，模型函数可以与 `model_clause` 一起使用。

模型功能有：

- `CV`
- `ITERATION_NUMBER`
- `PRESENTNNV`
- `PRESENTV`
- `PREVIOUS`

### 用户定义函数

您可以在 PL/SQL 或 Java 中使用用户定义函数，以提供 SQL 或 SQL 内置函数中不可用的功能。SQL 函数和用户定义函数可以出现在任何地方，即任何可以出现表达式的地方。

例如，它可以用于：

- `SELECT` 语句的 `SELECT` 列表。
- `WHERE` 子句的条件。
- 连接方式、订购方式、开始方式和分组方式
- `INSERT` 语句的 `VALUES` 子句。
- `UPDATE` 语句的 `SET` 子句。

基本上我们使用 `CREATE FUNCTION` 在 SQL 中创建用户定义的函数。

### 标量函数

可以在 SQL 中使用标量函数根据输入值返回单个值。

```sql
Input: SELECT UCASE(geeksforgeeks);
Output: GEEKSFORGEEKS
```

最常用的标量函数是 `UCASE()` 将字段转换为大写，`LCASE()` 将字段转换为小写，`LEN()` 查找文本字段的长度，`ROUND()` 对指定的小数位数进行舍入，`NOW()` 查找当前系统日期和时间。