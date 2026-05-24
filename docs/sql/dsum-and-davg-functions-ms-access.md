# DSum()和 DAvg()功能 MS 访问

> 原文:[https://www . geesforgeks . org/dsum-and-davg-functions-ms-access/](https://www.geeksforgeeks.org/dsum-and-davg-functions-ms-access/)

**1。DSum()函数:**
在 MS Access 中，DSum()函数用于计算一组指定记录(一个域)中一组值的和。DSum 函数从满足条件的字段中返回一组值的总和。d Sum 和 Sum 的区别在于，在 DSum 函数中，在对数据进行分组之前计算值，而在 Sum 函数中，在计算字段表达式中的值之前对数据进行分组。

**语法:**

```sql
DSum (expr, domain [, criteria])

```

**参数:**该方法接受三参数，如上所述，描述如下:

*   **expr :** 标识数值要合计的数值字段。它可以是标识表或查询中的字段的字符串表达式，也可以是对该字段中的数据执行计算的表达式。在 expr 中，可以包含表中字段的名称、窗体上的控件、常数或函数。如果 expr 包含一个函数，它可以是内置的或用户定义的，但不能是另一个域聚合或 SQL 聚合函数。
*   **域:**它是一个字符串表达式，标识构成域的记录集。它可以是表名，也可以是不需要参数的查询的查询名。
*   **标准:**它标识一个字符串表达式，用于限制执行 DSum 函数的数据范围。它是可选的。它是应用于域的 WHERE 子句。

**返回:**返回满足条件的指定记录集中所有值的总和。如果没有记录满足条件参数，或者如果域不包含记录，DSum 函数将返回一个 Null。

**表–产品详情:**

| 产品标识 | 产品 _ 价格 |
| --- | --- |
| One hundred and one | Fifteen thousand |
| One hundred and two | ten thousand |
| One hundred and three | Eleven thousand |
| One hundred and four | Six thousand |

**例-1 :** 求所有产品价格之和。

```sql
Select DSum("Product_Price", "Product Details") as Total_Price;

```

**输出:**

| 总价 |
| --- |
| Forty-two thousand |

**例-2 :** 求给定条件下产品 id 小于 103 的产品价格之和。

```sql
Select DSum("Product_Price", "Product Details", "Product_Id  < 103") as Total_Price;

```

**输出:**

| 总价 |
| --- |
| Twenty-five thousand |

**2。DAvg()函数:**
在 MS Access 中，DAvg()函数用于计算指定记录集(一个域)中一组值的平均值。DAvg 函数返回满足条件的字段中一组值的平均值。DAvg 和 Avg 的区别在于，在 d Avg 函数中，在对数据进行分组之前对值进行平均，而在 Avg 函数中，在对字段表达式中的值进行平均之前对数据进行分组。

**语法:**

```sql
DAvg (expr, domain [, criteria])

```

**参数:**该方法接受三参数，如上所述，描述如下:

*   **表达式:**它标识要取平均值的数值字段。它可以是标识表或查询中的字段的字符串表达式，也可以是对该字段中的数据执行计算的表达式。在 expr 中，可以包含表中字段的名称、窗体上的控件、常数或函数。如果 expr 包含一个函数，它可以是内置的或用户定义的，但不能是另一个域聚合或 SQL 聚合函数。
*   **域:**它是一个字符串表达式，标识构成域的记录集。它可以是表名，也可以是不需要参数的查询的查询名。
*   **标准:**它标识用于限制执行 DAvg 函数的数据范围的字符串表达式。它是可选的。它是应用于域的 WHERE 子句。

**返回:**返回满足条件的指定记录集中所有值的平均值。如果没有记录满足条件参数，DAvg 函数返回一个 Null。

**表–产品详情:**

| 产品标识 | 产品 _ 价格 |
| --- | --- |
| One hundred and one | ten thousand |
| One hundred and two | Twenty thousand |
| One hundred and three | thirty thousand |
| One hundred and four | forty thousand |

**例-1 :** 求产品价格的平均值。

```sql
Select DAvg("Product_Price", "Product Details") as Avg_Price;

```

**输出:**

| 平均价格 |
| --- |
| Twenty-five thousand |

**例-2 :** 求给定条件下产品 id 小于 103 的产品价格平均值。

```sql
Select DAvg("Product_Price", "Product Details", "Product_Id  < 103") as Avg_Price;

```

**输出:**

| 平均价格 |
| --- |
| Fifteen thousand |