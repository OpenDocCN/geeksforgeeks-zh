# MySQL 中的 ASIN()和 ACOS()函数

> 原文:[https://www . geesforgeks . org/asin-and-acos-function-in-MySQL/](https://www.geeksforgeeks.org/asin-and-acos-function-in-mysql/)

**1。ASIN()函数:**
MySQL 中的 ASIN() [函数](https://www.geeksforgeeks.org/sql-functions-aggregate-scalar-functions/)用来返回[ -1，1]范围内任意数字的反正弦。如果数字不在-1 到 1 的范围内，则返回空值。

**语法:**

```sql
ASIN(X)

```

**参数:**
ASIN()函数接受一个参数，如上所述，如下所述。

*   **X–**我们要计算其反正弦的数字。它应该在[-1，1]的范围内。

**返回:**
返回给定数字 x 的反正弦

**示例-1 :**
使用 ASIN()函数求 1 的反正弦。

```sql
SELECT ASIN(1) AS Asin_Val ;

```

**输出:**

| Asin_Val 参数 |
| --- |
| 1.5707963267948966 |

**示例-2 :**
使用 ASIN()函数对(0，1)范围内的数字进行反正弦运算。

```sql
SELECT ASIN(0.25) AS Asin_Val;

```

**输出:**

| Asin_Val 参数 |
| --- |
| 0.25268025514207865 |

**示例-3 :**
使用 ASIN()函数对(0，-1)范围内的数字进行反正弦运算。

```sql
SELECT ASIN(-0.35) AS Asin_Val;

```

**输出:**

| Asin_Val 参数 |
| -0.35757110364551026 |

**示例-4 :**
使用 ASIN()函数计算不在[0，-1]范围内的数字的反正弦。

```sql
SELECT ASIN(2.75) AS Asin_Val ;

```

**输出:**

| Asin_Val 参数 |
| --- |
| 空 |

**示例-5 :**
表中数值列的反正弦值。

**表-编号**

| X |
| --- |
| -2 |
| -1 |
| -0.50 |
| Zero |
| Zero point five |
| one |
| Two |

```sql
SELECT X, ASIN(X) AS ArcSin_X  FROM Number ;

```

**输出:**

| X | 反正切 _X |
| --- | --- |
| -5 | 空 |
| -1 | -1.5707963267948966 |
| -0.50 | -0.5235987755982989 |
| Zero | Zero |
| Zero point five | 0.5235987755982989 |
| one | 1.5707963267948966 |
| Two | 空 |

**2。ACOS()函数:**
()ACOS()[函数在 MySQL 中](https://www.geeksforgeeks.org/aggregate-functions-in-sql/?ref=rp)用于返回【-1，1】范围内任意数字的弧余弦。如果数字不在-1 到 1 的范围内，则返回空值。

**语法:**

```sql
ACOS(X)

```

**参数:**
ACOS(X)函数接受一个参数，在 ACOS(X)函数中 X 为参数。让我们借助例子来理解。

*   **X–**我们要计算其弧余弦的数字。它应该在[-1，1]的范围内。

**返回:**
返回给定数字 x 的弧余弦

**例-1 :**
使用 ACOS()函数求 1 的弧余弦。

```sql
SELECT ACOS(1) AS Acos_Val;

```

**输出:**

| S7-1200 可编程控制器 |
| --- |
| Zero |

**示例-2 :**
使用 ACOS()函数对(0，1)范围内的数字进行弧余弦运算。

```sql
SELECT ACOS(0.75) AS Acos_Val;

```

**输出:**

| S7-1200 可编程控制器 |
| --- |
| 0.7227342478134157 |

**示例-3 :**
使用 ACOS()函数对(0，-1)范围内的一个数进行弧余弦运算。

```sql
SELECT ACOS(-0.75) AS Acos_Val ;

```

**输出:**

| S7-1200 可编程控制器 |
| --- |
| 2.4188584057763776 |

**示例-4 :**
使用 ACOS()函数对不在[0，-1]范围内的数字进行弧余弦运算。

```sql
SELECT ACOS(2.75) AS Acos_Val;

```

**输出:**

| S7-1200 可编程控制器 |
| --- |
| 空 |

**示例-5 :**
表中数值列的弧余弦值。

**表-编号**

| X |
| --- |
| -5 |
| -1 |
| -0.50 |
| Zero |
| Zero point five |
| one |
| Two |

```sql
SELECT X, ACOS(X) AS Acos_Val  FROM Number;

```

**输出:**

| X | S7-1200 可编程控制器 |
| --- | --- |
| -5 | 空 |
| -1 | 3.141592653589793 |
| -0.50 | 2.0943951023931957 |
| Zero | 1.5707963267948966 |
| Zero point five | 1.0471975511965979 |
| one | Zero |
| Two | 空 |