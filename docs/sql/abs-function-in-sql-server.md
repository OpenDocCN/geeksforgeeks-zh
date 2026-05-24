# SQL Server 中的 ABS()函数

> 原文:[https://www.geeksforgeeks.org/abs-function-in-sql-server/](https://www.geeksforgeeks.org/abs-function-in-sql-server/)

**ABS()功能:**

**SQL Server** 中的这个函数用于返回指定数字的绝对值。绝对值用于描述数字线上的数字与 0 之间的距离。不考虑数字从零开始的方向，因为数字的绝对值从来不是负数。此函数将可以隐式转换为数字数据类型的任何数字数据类型或非数字数据类型作为参数。此函数返回的值的数据类型与参数的数值数据类型相同。

**特征:**

*   This function is used to find the absolute value of a specified number.
*   This function accepts a single parameter.
*   The accepted parameter is a numeric data type or any non-numeric data type that can be implicitly converted to a numeric data type.
*   The return value is of the same numeric data type as the specified parameter.

**语法:**

```sql
SELECT ABS(number);
```

**参数:**

该方法接受如下参数:

*   **Number:** will return the specified value of its absolute value.

**返回:**

它返回指定数字的绝对值。

**示例-1 :**

获取指定数字 0 的绝对值 0。

```sql
SELECT ABS(0);
```

**输出:**

```sql
0
```

**示例-2 :**

获取指定数字的绝对值. 7-0.7

```sql
SELECT ABS(-0.7);
```

**输出:**

```sql
.7
```

**示例-3 :**

使用带变量的 ABS()函数，得到指定数字 123 的绝对值 123。

```sql
DECLARE @Parameter_Value INT;
SET @Parameter_Value = 123;
SELECT ABS(@Parameter_Value);
```

**输出:**

```sql
123
```

**示例-4 :**

使用带变量的 ABS()函数，得到指定浮点值“-34.87”的绝对值 34.87。

```sql
DECLARE @Parameter_Value float;
SET @Parameter_Value = -34.87;
SELECT ABS(@Parameter_Value);
```

**输出:**

```sql
34.869999999999997
```

**应用:**

此函数用于返回指定数值的绝对值。