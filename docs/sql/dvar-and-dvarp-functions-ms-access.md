# DVar()和 DVarP()功能 MS 访问

> 原文:[https://www . geesforgeks . org/dvar-and-dvarp-functions-ms-access/](https://www.geeksforgeeks.org/dvar-and-dvarp-functions-ms-access/)

**1。DVar()函数:**
MS Access 中的 DVar()函数用于估计指定记录集(一个域)中一组值的方差。DVar 函数评估总体样本的方差。

**语法:**

```sql
DVar (expr, domain, criteria)

```

**参数:**

该方法接受三个参数，如上所述，如下所述:

*   **expr :** 它标识我们要为其找到方差的字段。它可以是标识表或查询中的字段的字符串表达式，也可以是对该字段中的数据执行计算的表达式。
*   **域:**标识构成域的记录集。它可以是表名，也可以是不需要参数的查询的查询名。
*   **标准:**它标识了一个字符串表达式，用于限制执行 DVar 功能的数据范围。它是可选的。它是应用于域的 WHERE 子句。

**返回:**如果域引用的记录少于两个，或者满足条件的记录少于两个，则 DVar 函数返回空值，表示无法计算方差。否则，它返回整个总体样本的方差。

**表–产品销售:**

| 产品标识 | 产品 _ 价格 |
| --- | --- |
| One hundred and one | ten thousand |
| One hundred and two | Eleven thousand |
| One hundred and three | Twelve thousand |
| One hundred and four | Thirteen thousand |

**例-1 :** 产品价格的方差。

```sql
SELECT DVar("Product_Price", "ProductSales") AS DVar_Value ;

```

**输出:**

| DVar_Value |
| --- |
| 1666666.6666667 |

**例-2 :** 价格小于 12500 的产品价格的方差。

```sql
SELECT DVar("Product_Price", "ProductSales", "Product_Price<12500") AS DVar_Value ;

```

**输出:**

| DVar_Value |
| --- |
| One million |

**2。功能:**
移动台接入中的功能用于估计指定记录集(一个域)中一组值的方差。DVarP 函数计算整个群体的方差。

DVar 和 Dvar 之间的主要区别在于，Dvar 函数评估整个群体的方差，而 Dvar 函数评估整个群体样本的方差。

**语法:**

```sql
DVarP (expr, domain, criteria)

```

**参数:**
该方法接受三参数，如上所述，描述如下:

*   **expr :** 它标识我们要为其找到方差的字段。它可以是标识表或查询中的字段的字符串表达式，也可以是对该字段中的数据执行计算的表达式。
*   **域:**标识构成域的记录集。它可以是表名，也可以是不需要参数的查询的查询名。
*   **标准:**它标识一个字符串表达式，用于限制执行 DVarP 功能的数据范围。它是可选的。它是应用于域的 WHERE 子句。

**返回:**如果域引用的记录少于两个，或者满足条件的记录少于两个，则 DVarP 函数返回空值，表示无法计算方差。否则，它返回整个群体的方差。

**注意:**在 DVar 或 DVarP 函数中，在对数据进行分组之前计算值，而在 Var 或 VarP 函数中，在计算字段表达式中的值之前对数据进行分组。

**表–示例详细信息:**

| 子 Id | 马克斯（英格兰人姓氏） |
| --- | --- |
| one | Eighty-eight |
| Two | Ninety-five |
| three | Ninety-six |
| four | One hundred |

**例-1 :** 标记的方差。

```sql
SELECT DVarP("Marks", "ExamDetails ") AS DVarP_Value ;

```

**输出:**

| DVarP_Value |
| --- |
| 18.6875 |

**例-2 :** 标记的方差为> 90。

```sql
SELECT DVarP("Marks", "ExamDetails ", "Marks>90") AS DVarP_Value ;

```

**输出:**

| DVarP_Value |
| --- |
| 4.6666666666667 |