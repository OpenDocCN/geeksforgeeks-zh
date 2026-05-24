# DMin 和 DMax 功能 MS 访问

> 原文:[https://www . geeksforgeeks . org/dmin-and-dmax-functions-ms-access/](https://www.geeksforgeeks.org/dmin-and-dmax-functions-ms-access/)

**1。DMin()功能:**

MS Access 中的 DMin()函数用于确定一组指定记录(一个域)中的最小值。DMin 函数返回满足标准的最小值。如果表达式识别数值数据，DMin 函数返回数值。如果表达式识别字符串数据，它们将返回按字母顺序排列的第一个字符串。DMin 函数和最小函数的区别在于，在 d Min 函数中，在对数据进行分组之前先对值进行评估，而在最小函数中，在对字段表达式中的值进行评估之前先对数据进行分组。

```sql
Syntax : DMin ( expr , domain , criteria)
```

**参数:**

该方法接受三个参数，如上所述，如下所述:

*   **expr–**它标识了我们想要找到最小值的字段。它可以是标识表或查询中的字段的字符串表达式，也可以是对该字段中的数据执行计算的表达式。
*   **域–**它标识构成域的记录集。它可以是表名，也可以是不需要参数的查询的查询名。
*   **标准–**它标识一个字符串表达式，用于限制执行 DMin 函数的数据范围。它是可选的。它是应用于域的 WHERE 子句。

**返回**:

它返回指定记录集中的最小值。

**表-产品详情。**

| 产品标识 | 产品 _ 价格 |
| --- | --- |
| One hundred and one | ten thousand |
| One hundred and two | Eleven thousand |
| One hundred and three | Five thousand |
| One hundred and four | Seven thousand |

**示例-1 :**
寻找最低产品价格

```sql
Select DMin("Product_Price", "ProcuctDetails") as Min_Price;

```

**输出:**

| 最低价格 |
| --- |
| Five thousand |

**示例-2 :**
查找给定条件下的最小产品价格，其中产品 id 为 104。

```sql
Select DMin("Product_Price", "ProcuctDetails","Product_Id  = 104") as Min_Price;

```

**输出:**

| 最低价格 |
| --- |
| Seven thousand |

**2。DMax()功能–**

MS Access 中的 DMax()函数用于确定一组指定记录(一个域)中的最大值。DMax 函数返回满足标准的最大值。如果 expr 识别数字数据，DMax 函数返回数字值。如果 expr 识别字符串数据，它们会返回按字母顺序排在最后的字符串。d Max 和 Max 的区别在于，在 DMax 函数中，在对数据进行分组之前对值进行评估，而在 Max 函数的情况下，在对字段表达式中的值进行评估之前对数据进行分组。

**语法–**

```sql
DMax( expr , domain , criteria)
```

**参数:**

该方法接受三个参数，如上所述，如下所述:

*   **expr–**它标识了我们想要找到最大值的字段。它可以是标识表或查询中的字段的字符串表达式，也可以是对该字段中的数据执行计算的表达式。
*   **域–**它标识构成域的记录集。它可以是表名，也可以是不需要参数的查询的查询名。
*   **标准–**它标识一个字符串表达式，用于限制执行 DMax 函数的数据范围。它是可选的。它是应用于域的 WHERE 子句。

**返回**:

它返回指定记录集中的最大值。

**表-产品详情。**

| 产品标识 | 产品 _ 价格 |
| --- | --- |
| One hundred and one | ten thousand |
| One hundred and two | Eleven thousand |
| One hundred and three | Five thousand |
| One hundred and four | Seven thousand |

**例-1 :**
求最高产品价格。

```sql
Select DMax("Product_Price", "ProcuctDetails") as Max_Price;

```

**输出:**

| 最高价格 |
| --- |
| Eleven thousand |

**例-2 :**
求给定条件下产品 id 为 103 的最大产品价格。

```sql
Select DMax("Product_Price", "ProcuctDetails","Product_Id  = 103") as Max_Price;

```

**输出:**

| 最高价格 |
| --- |
| Five thousand |