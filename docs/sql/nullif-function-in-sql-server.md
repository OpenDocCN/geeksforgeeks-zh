# SQL Server 中的 NULLIF()函数

> 原文:[https://www . geesforgeks . org/null if-function-in-SQL-server/](https://www.geeksforgeeks.org/nullif-function-in-sql-server/)

**零():**

SQL Server 中的这个函数用于检查两个指定的表达式是否相等。

**特征:**

*   This function is used to check whether two given expressions are equal.
*   If the given two expressions are equal, the function returns a null value.
*   If the given two expressions are not equal, this function returns the first expression.
*   This function is an advanced function.
*   This function takes two parameters, the first expression and the second expression.

**语法:**

```sql
NULLIF(expr1, expr2)
```

**参数:**

此方法接受两个参数。

*   **Expression 1 and Expression 2 –** The specified expressions to be compared.

**返回:**

如果给定的两个表达式相等，则返回空值；否则，如果给定的两个表达式不相等，则返回第一个表达式。

**示例-1 :**

使用 NULLIF()函数并获取输出。

```sql
SELECT NULLIF(11, 11);
```

**输出:**

```sql
NULL
```

这里，返回空值，因为两个表达式相等。

**示例-2 :**

使用 NULLIF()函数并获取输出。

```sql
SELECT NULLIF('ab', 'abc');
```

**输出:**

```sql
ab
```

这里，“ab”作为输出返回，因为所述表达式不相等。

**示例-3 :**

使用 NULLIF()函数，并使用变量获取输出。

```sql
DECLARE @exp1 VARCHAR(50);
DECLARE @exp2 VARCHAR(50);
SET @exp1 = '2021/01/08';
SET @exp2 = '2021/01/08';
SELECT NULLIF(@exp1, @exp2);
```

**输出:**

```sql
NULL
```

**示例-4 :**

使用 NULLIF()函数，使用 CAST()函数获取输出。

```sql
SELECT NULLIF(11, CAST(11.65 AS int));
```

**输出:**

```sql
NULL
```

**应用:**

这个函数用来测试两个表达式是否相等。