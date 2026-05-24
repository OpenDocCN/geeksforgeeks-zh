# MySQL 中的 SQRT()函数

> 原文:[https://www.geeksforgeeks.org/sqrt-function-in-mysql/](https://www.geeksforgeeks.org/sqrt-function-in-mysql/)

**SQRT()** 是 MySQL 中的[函数](https://www.geeksforgeeks.org/sql-functions-aggregate-scalar-functions/)用来返回给定非负数的平方根。如果数字为负，则返回空值。

**语法:**

```sql
SQRT(X)

```

**参数:**
MySQL 中的 SQRT 函数接受一个参数，根据输入给出结果。在下面给出的示例中，您将看到如何在函数中给出输入，以及成功执行后它到底返回了什么。

*   **X–**我们要计算其平方根的数字。

**返回–**
返回给定非负数的平方根。

**示例-1 :**
将 SQRT()函数应用于一个平方数。

```sql
SELECT SQRT(4) AS Root_Val;

```

**输出:**

| Root_Val |
| --- |
| Two |

**示例-2 :**
将 SQRT()函数应用于非平方数。

```sql
SELECT SQRT(14) AS Root_Val;

```

**输出:**

| Root_Val |
| --- |
| 3.7416573867739413 |

**示例-3 :**
对负数应用 SQRT()函数。

```sql
SELECT SQRT(-14) AS Root_Val;

```

**输出:**

| Root_Val |
| --- |
| 空 |

**示例-4 :**
将 SQRT()函数应用于表中的数值列。

**表-编号**

| X |
| --- |
| one |
| Zero |
| Eighty-one |
| Fifty-four |
| Sixty-five point four two |
| -10 |

```sql
SELECT X, SQRT(X) AS X_Root  FROM Number ;

```

**输出:**

| X | X_Root |
| --- | --- |
| one | one |
| Zero | Zero |
| Eighty-one | nine |
| Fifty-four | 7.3484692283495345 |
| Sixty-five point four two | 8.088263101556477 |
| -10 | 空 |