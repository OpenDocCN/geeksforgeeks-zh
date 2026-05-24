# SQL Server 中的 PI()函数

> 原文:[https://www.geeksforgeeks.org/pi-function-in-sql-server/](https://www.geeksforgeeks.org/pi-function-in-sql-server/)

**PI()功能:**

**SQL Server** 中的这个函数用来返回数学 Pi 的常量浮点值。显示的默认小数位数是七，但 SQL Server 在内部使用完整的双精度值。

**特征:**

*   This function is used to get the value of pi.
*   This function does not accept any parameters.
*   Any type of mathematical operation can be done with this function, such as addition, multiplication and so on.

**语法:**

```sql
PI()
```

**参数:**

此方法不接受任何参数。

**返回:**

它返回π值。

**示例-1 :**

获取 pi 的默认值。

```sql
SELECT PI();
```

**输出:**

```sql
3.1415926535897931
```

**示例-2 :**

以加值为 2 的 pi()函数为变量，加 2 后得到 PI 的值。

```sql
DECLARE @Parameter_Value INT;
SET @Parameter_Value = 2;
SELECT PI() + @Parameter_Value;
```

**输出:**

```sql
5.1415926535897931
```

**示例-3 :**

减去 1 后得到圆周率的值。

```sql
SELECT PI() - 1;
```

**输出:**

```sql
2.1415926535897931
```

**示例-4 :**

获取 pi 的默认值，直到小数点后 3 位。

```sql
SELECT ROUND(PI(), 3) As New;
```

**输出:**

```sql
3.1419999999999
```

**应用:**

该函数用于返回 Pi 值。