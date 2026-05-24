# SQL Server 中的 EXP()函数

> 原文:[https://www.geeksforgeeks.org/exp-function-in-sql-server/](https://www.geeksforgeeks.org/exp-function-in-sql-server/)

**EXP()功能:**

**SQL Server** 中的这个函数用于返回一个值，该值是 **e** 的 n 次方，其中 n 是一个指定的数字。这里的“ **e** ”是一个数学常数，是取值为 2.7182818 的自然对数的基数，n 是作为函数参数的输入数。

**特征:**

该函数用于查找 **e** 升至 n 次方的值。

这里取值 **n，**作为函数的参数。

这里的“ **e** ”是一个数学常数，是取值为“2.7182818”的自然对数的基数。

该函数使用公式“ **(e) <sup>n</sup> =返回值**”。

**语法:**

```sql
SELECT EXP(number);
```

**参数:**

该方法接受如下参数:

*   **Number: the power number specified by** .

**返回:**

它返回一个“e”的 n 次方值，其中 n 是一个指定的数字。

**示例-1 :**

得到值 1.0，即“e”的 0 次方。

```sql
SELECT EXP(0);
```

**输出:**

```sql
1.0
```

**示例-2 :**

得到值 2.7182818284590451，它是“e”的一次幂。

```sql
SELECT EXP(1) As New;
```

**输出:**

```sql
2.7182818284590451
```

**示例-3 :**

使用带有变量的 EXP()函数，得到值 11.023176380641601，该值是“e”的 2.4 次方。

```sql
DECLARE @Parameter_Value Float;
SET @Parameter_Value = 2.4;
SELECT EXP(@Parameter_Value);
```

**输出:**

```sql
11.023176380641601
```

**示例-4 :**

使用带有变量的 EXP()函数，得到值 0.1353352832366127，该值被“e”提升为(-2)次方。

```sql
DECLARE @Parameter_Value int;
SET @Parameter_Value = -2;
SELECT EXP(@Parameter_Value);
```

**输出:**

```sql
0.1353352832366127
```

**应用:**

这个函数用来返回一个“e”的 n 次方值，其中 n 是一个指定的数字。