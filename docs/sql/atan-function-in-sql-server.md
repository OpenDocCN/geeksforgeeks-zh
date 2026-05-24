# SQL Server 中的 ATAN()函数

> 原文:[https://www.geeksforgeeks.org/atan-function-in-sql-server/](https://www.geeksforgeeks.org/atan-function-in-sql-server/)

**ATAN()功能:**

**SQL Server** 中的这个函数用于返回指定值的反正切或反正切。这个函数只接受一个参数，这个参数是一个数字，参数的范围是无限的。

此函数返回-pi/2 到 pi/2 范围内的值，以弧度表示。此函数将任何数字数据类型以及可以隐式转换为数字数据类型的任何非数字数据类型作为参数。

**特征:**

*   该函数用于求指定值的反正切或反正切。
*   该函数接受单个参数。
*   可接受的参数范围是无限的。
*   该函数给出的值在-pi/2 到 pi/2 的范围内。
*   返回值将以弧度为单位。

**语法:**

```sql
SELECT ATAN(number);
```

**参数:**

该方法接受如下参数:

*   **Number: the value specified by** , whose arctangent will be returned.

**返回:**

它返回指定值的反正切或反正切。

**示例-1 :**

获取指定值的反正切-1

```sql
SELECT ATAN(-1);
```

**输出:**

```sql
-0.78539816339744828
```

**示例-2 :**

获取指定值的反正切 45

```sql
SELECT ATAN(45);
```

**输出:**

```sql
1.5485777614681775
```

**示例-3 :**

使用带有变量的 ATAN()函数并获得指定值 0 的反正切。

```sql
DECLARE @Parameter_Value INT;
SET @Parameter_Value = 0;
SELECT ATAN(@Parameter_Value);
```

**输出:**

```sql
0.0
```

**示例-4 :**

使用带有变量的 ATAN()函数，并获得指定浮点值“0.45”的反正切。

```sql
DECLARE @Parameter_Value float;
SET @Parameter_Value = 0.45;
SELECT ATAN(@Parameter_Value);
```

**输出:**

```sql
0.42285392613294071
```

**应用:**

该函数用于返回指定值的反正切或反正切。