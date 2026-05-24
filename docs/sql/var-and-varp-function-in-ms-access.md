# 移动台接入中的 Var()和 VarP()功能

> 原文:[https://www . geesforgeks . org/var-and-varp-function-in-ms-access/](https://www.geeksforgeeks.org/var-and-varp-function-in-ms-access/)

**1。Var()函数:**
MS Access 中的 Var()函数用于估计总体样本的方差。

**语法:**

```sql
Var(expr)
```

**参数:**该方法接受一个参数，如上所述，如下所述:

*   **表达式**:它表示一个字符串表达式，用于标识包含我们要计算的数值数据的字段，或者表示使用该字段中的数据执行计算的表达式。expr 中的操作数可以包括表字段、常数或函数的名称。

**返回:**计算总体样本的方差。

**注意:**如果基础查询包含少于两个记录或没有记录，则它返回空值，表示无法计算方差。

**表–**产品详情

| 产品标识 | 产品 _ 价格 |
| --- | --- |
| One hundred thousand | Ninety |
| Two hundred thousand and one | Eighty-one |
| Two hundred and ninety-eight thousand seven hundred | Thirty-four |
| Three hundred and forty-five thousand six hundred and thirty-two | Eighty-four |

**例-1 :**
产品价格的方差。

```sql
SELECT Var(Product_Price) AS Var_Value 
FROM ProcuctDetails;
```

**输出:**

| 风险值 |
| --- |
| Six hundred and sixty-four point two five |

**示例-2 :**
仅一条记录的方差。

```sql
SELECT Var(100) AS Var_Value ;
```

**输出:**

| 风险值 |
| --- |
|  |

所以，我们可以看到它是无法计算的。

**2。VarP()函数:**
MS Access 中的 VarP()函数用于估计一个群体的方差。VarP()函数和 VarP()函数之间的主要区别是 VarP 评估总体，而 Var 函数评估总体样本。

**语法:**

```sql
VarP(expr)
```

**参数:**该方法接受一个参数，如上所述，如下所述:

*   **表达式**:它表示一个字符串表达式，用于标识包含我们要计算的数值数据的字段，或者表示使用该字段中的数据执行计算的表达式。expr 中的操作数可以包括表字段、常数或函数的名称。

**返回:**计算总体的方差。

**注意:**如果基础查询包含少于两个记录，则它返回空值，表示无法计算标准偏差。

**表–**产品

| P_Id | 用于微机系列的通用电路分析程序（Simulation Program with Integrated Circuit Emphasis 的缩写） |
| --- | --- |
| One thousand and one | Fifty-five |
| One thousand and five | Twenty |
| One thousand and eight | Sixty-six |

**示例-1 :**

```sql
SELECT VarP (P_Price) AS VarP_Value 
FROM Procucts;
```

**输出:**

| 变量 _ 值 |
| --- |
| 384.666666666667 |

**示例-2 :**

```sql
SELECT VarP (10) AS VarP_Value;
```

**输出:**

| 变量 _ 值 |
| --- |
|  |