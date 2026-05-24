# MySQL 中的 SIGN()函数

> 原文:[https://www.geeksforgeeks.org/sign-function-in-mysql/](https://www.geeksforgeeks.org/sign-function-in-mysql/)

MySQL 中的 SIGN() [函数](https://www.geeksforgeeks.org/sql-functions-aggregate-scalar-functions/)用来返回给定数字的符号。如果数字为正数，则返回 1；如果数字为负数，则返回-1；如果数字为零，则返回 0。

**语法:**

```sql

SIGN(X)

```

**参数:**
SIGN()函数接受一个参数作为输入，并以正值(+1)、负值(-1)和零值(0)的形式给出结果。

*   **X–**我们要检查其符号的数字。

**返回–**
返回给定数字的符号值，即正(+1)、负(-1)和零(0)。

**示例-1 :**
将 SIGN()函数应用于零。

```sql
SELECT SIGN(0) AS Sign_Val;

```

**输出:**

| 信号 |
| --- |
| Zero |

**示例-2 :**
将 SIGN()函数应用于正数。

```sql
SELECT SIGN(12) AS Sign_Val;

```

**输出:**

| 信号 |
| --- |
| one |

**示例-3 :**
对负数应用 SIGN()函数。

```sql
SELECT SIGN(-2) AS Sign_Val;

```

| 信号 |
| --- |
| -1 |

**示例-4 :**
将 SIGN()函数应用于表中的数值列。

**表-编号**

| X |
| --- |
| +12 |
| One point eight |
| Zero |
| -1.8 |
| -14 |

```sql
SELECT X, SIGN(X) AS X_Sign  FROM Number;

```

**输出:**

| X | x _ 符号 |
| --- | --- |
| Twelve | one |
| One point eight | one |
| Zero | Zero |
| -1.8 | -1 |
| -14 | -1 |