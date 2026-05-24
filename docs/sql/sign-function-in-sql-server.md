# SQL Server 中的 SIGN()函数

> 原文:[https://www.geeksforgeeks.org/sign-function-in-sql-server/](https://www.geeksforgeeks.org/sign-function-in-sql-server/)

**SIGN()函数:**
这个函数在 **SQL Server** 中用来返回指定数字的符号。如果数字为正数，则返回 1；如果数字为负数，则返回-1；如果数字为零，则返回 0。

**特征:**

*   该函数用于寻找给定数字的符号，即给定数字是正的、负的还是零。
*   该函数只接受所有类型的数字，即正、负、零。
*   这个函数也接受分数。
*   如果数字为正数，此函数总是返回 1；如果数字为负数，则返回-1；如果数字为零，则返回 0。

**语法:**

```sql
SIGN(number)
```

**参数:**
该方法接受如下参数:

*   **编号:**返回标志的指定编号。

**返回:**
返回指定数字的符号。

**示例-1 :**
获得结果为 1，即指定数字 2 为正。

```sql
SELECT SIGN(2);
```

**输出:**

```sql
1
```

**示例-2 :**
获取结果为-1，即指定数字-7 为负数。

```sql
SELECT SIGN(-7);
```

**输出:**

```sql
-1
```

**示例-3 :**
使用带有变量的 SIGN()函数，得到指定数字 0 的结果为 0。

```sql
DECLARE @Parameter_Value INT;
SET @Parameter_Value = 0;
SELECT SIGN(@Parameter_Value);

```

**输出:**

```sql
0
```

**例-4 :**
得到的结果为 1，即“5/2”的结果为正。

```sql
SELECT SIGN(5/2);
```

**输出:**

```sql
1
```

**示例-5 :**
使用带有变量的 SIGN()函数，得到的结果为 1，即浮点值“5.75”为正。

```sql
DECLARE @Parameter_Value FLOAT;
SET @Parameter_Value = 5.75;
SELECT SIGN(@Parameter_Value);

```

**输出:**

```sql
1.0
```

**应用:**
此功能用于返回指定数字的符号。