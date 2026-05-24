# SQL Server 中的 POWER()函数

> 原文:[https://www.geeksforgeeks.org/power-function-in-sql-server/](https://www.geeksforgeeks.org/power-function-in-sql-server/)

**POWER()函数:**
这个函数在 **SQL Server** 中用于将指定的指数提升到指定的基数后返回一个结果。例如，如果基数为 5，指数为 2，这将返回 25 的结果。

**特征:**

*   此函数用于在将指定指数提升到指定基数后查找结果。
*   这个函数接受两个参数基数和指数。
*   基值可以是负值，但不能是指数值。
*   基数和指数值可以是分数。
*   该函数使用公式
    **“(基数)
    <sup>(指数)</sup> =返回值”。** 

**语法:**

```sql
POWER(a, b)
```

**参数:**
该方法接受如下两个参数:

*   **a :** 指定的基数。
*   **b :** 指定的指数。

**返回:**
将指定的指数数提升到指定的基数后返回一个结果。

**示例-1 :**
对基值 7 和指数值 2 得到 49 的结果。

```sql
SELECT POWER(7, 2);
```

**输出:**

```sql
49
```

**例-2 :**
取 3 的 27 作为基数和指数值。

```sql
SELECT POWER(3, 3);
```

**输出:**

```sql
27
```

**示例-3 :**
使用带变量的 POWER()函数，得到基值 6 和指数值 0 的结果 1。

```sql
DECLARE @Base_Value INT;
DECLARE @Exponent_Value INT;
SET @Base_Value = 6;
SET @Exponent_Value = 0;
SELECT POWER(@Base_Value, @Exponent_Value);

```

**输出:**

```sql
1
```

**示例-4 :**
获取基值 0 和指数值 4 的 0 结果。

```sql
SELECT POWER(0, 4);
```

**输出:**

```sql
0
```

**示例-5 :**
获取基值-4 和指数值 3 的-64 结果。

```sql
SELECT POWER(-4, 3);

```

**输出:**

```sql
-64
```

**示例-6 :**
使用带变量的 POWER()函数，得到基础浮点值 2.1 和指数浮点值 4.5 的结果为 28.2。

```sql
DECLARE @Base_Value FLOAT;
DECLARE @Exponent_Value FLOAT;
SET @Base_Value = 2.1;
SET @Exponent_Value = 4.5;
SELECT POWER(@Base_Value, @Exponent_Value);

```

**输出:**

```sql
28.182974409756689
```

**应用:**
该函数用于将指定的指数提升到指定的基数后返回一个结果。