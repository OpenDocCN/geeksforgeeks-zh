# SQL Server 中的 SQRT()函数

> 原文:[https://www.geeksforgeeks.org/sqrt-function-in-sql-server/](https://www.geeksforgeeks.org/sqrt-function-in-sql-server/)

**SQRT()函数:**
这个函数在 **SQL Server** 中用来返回指定正数的平方根。**例如**，如果指定的数字是 81，该功能将返回 9。

**特征:**

*   这个函数用来求给定数字的平方根。
*   这个函数只接受正数。
*   这个函数也接受分数。
*   这个函数总是返回正数。
*   该函数使用公式“
    **(a) <sup>1/2</sup> =返回值** ，其中 a 为指定数字。

**语法:**

```sql
SQRT(number)
```

**参数:**
该方法接受如下参数:

*   **数字:**指定的正数，其平方根将被返回。

**返回:**
返回指定正数的平方根。

**例-1 :**
求指定数字 4 的平方根。

```sql
SELECT SQRT(4);
```

**输出:**

```sql
2.0
```

**例-2 :**
求指定数字 0 的平方根。

```sql
SELECT SQRT(0);
```

**输出:**

```sql
0.0
```

**示例-3 :**
使用带变量的 SQRT()函数，得到指定数字 1 的平方根。

```sql
DECLARE @Parameter_Value INT;
SET @Parameter_Value = 1;
SELECT SQRT(@Parameter_Value);
```

**输出:**

```sql
1.0
```

**例-4 :**
求 16 的平方根，是“64/4”的结果。

```sql
SELECT SQRT(64/4);
```

**输出:**

```sql
4.0
```

**示例-5 :**
使用带变量的 SQRT()函数，得到浮点值“4.7”的平方根。

```sql
DECLARE @Parameter_Value FLOAT;
SET @Parameter_Value = 4.7;
SELECT SQRT(@Parameter_Value);

```

**输出:**

```sql
2.16794833886788
```

**应用:**
此函数用于返回指定正数的平方根。