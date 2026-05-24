# MS 接入中的 StDev()和 StDevP()功能

> 原文:[https://www . geesforgeks . org/stdev-and-stdevp-function in-ms-access/](https://www.geeksforgeeks.org/stdev-and-stdevp-function-in-ms-access/)

**1。标准偏差()函数:**
标准偏差()函数用于估计总体样本的标准偏差。

**语法:**

```sql
StDev (expr)
```

**参数:**该方法接受一个参数，如上所述，如下所述:

*   **expr :** 它表示一个字符串表达式，用于标识包含我们要计算的数值数据的字段，或者表示使用该字段中的数据执行计算的表达式。expr 中的操作数可以包括表字段、常数或函数的名称。

**返回:**计算总体样本的标准差。
**注意:**如果基础查询包含少于两条记录或没有记录，则返回空值，表示无法计算标准偏差。

**表–**产品详情

| 产品标识 | 产品 _ 价格 |
| --- | --- |
| One hundred thousand | Ninety |
| Two hundred thousand and one | Eighty-one |
| Two hundred and ninety-eight thousand seven hundred | Thirty-four |
| Three hundred and forty-five thousand six hundred and thirty-two | Eighty-four |

**示例 1 :**
产品价格的标准偏差。

```sql
SELECT stDev(Product_Price) AS StDEV_Value FROM ProcuctDetails;
```

**输出:**

| StDEV _ 值 |
| --- |
| 25.7730479377197 |

**例 2 :**
只有一条记录的标准偏差。

```sql
SELECT stDev(100) AS StDEV_Value ;
```

**输出:**

| StDEV _ 值 |
| --- |
|  |

所以，我们可以看到它是无法计算的。

**2。功能:**
质谱中的功能用于估计人群的标准差。StDevP()函数和 StDev()函数之间的主要区别是 StDevP 计算总体，而 StDev 计算总体样本。

**语法:**

```sql
StDevP (expr)
```

**参数:**该方法接受一个参数，如上所述，如下所述:

*   **表达式**:它表示一个字符串表达式，用于标识包含我们要计算的数值数据的字段，或者表示使用该字段中的数据执行计算的表达式。expr 中的操作数可以包括表字段、常数或函数的名称。

**返回:**计算总体的标准差。

**注意:**如果基础查询包含少于两个记录，则它返回空值，表示无法计算标准偏差。

**表–**产品

| P_Id | 用于微机系列的通用电路分析程序（Simulation Program with Integrated Circuit Emphasis 的缩写） |
| --- | --- |
| One thousand and one | Fifty-five |
| One thousand and five | Twenty |
| One thousand and eight | Sixty-six |

**示例-1 :**

```sql
SELECT stDevP(P_Price) AS StDEVp_Value FROM Procucts;
```

**输出:**

| StDEVp_Value |
| --- |
| 24.0208242989286 |

**示例-2 :**

```sql
SELECT stDevP(10) AS StDEVp_Value;
```

**输出:**

| StDEVp_Value |
| --- |
|  |