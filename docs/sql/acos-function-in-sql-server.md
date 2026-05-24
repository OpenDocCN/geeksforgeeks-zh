# SQL Server 中的 ACOS()函数

> 原文:[https://www.geeksforgeeks.org/acos-function-in-sql-server/](https://www.geeksforgeeks.org/acos-function-in-sql-server/)

**ACOS()功能:**

**SQL Server** 中的这个函数是用来返回指定值的弧余弦或反余弦的。反余弦函数的输入必须在-1 和 1 之间(包括 1 和 1)，否则该函数返回空值。

**特征:**

*   This function is used to find the arc cosine or inverse cosine of the specified value.
*   This function accepts a single parameter.
*   The accepted parameters range from -1 to 1 (inclusive), otherwise this function returns a null value.
*   The return value will be in radians.

**语法:**

```sql
SELECT ACOS(number);
```

**参数:**

该方法接受如下参数:

*   **Number:** will return the specified value of the inverse cosine.

**返回:**

它返回指定值的反余弦值或反余弦值。

**示例-1 :**

获取指定值的反余弦-1

```sql
SELECT ACOS(-1);
```

**输出:**

```sql
3.1415926535897931
```

**示例-2 :**

获取指定值 1 的反余弦

```sql
SELECT ACOS(1);
```

**输出:**

```sql
0.0
```

**示例-3 :**

使用带有变量的 ACOS()函数，得到指定值 0 的反余弦值。

```sql
DECLARE @Parameter_Value INT;
SET @Parameter_Value = 0;
SELECT ACOS(@Parameter_Value);
```

**输出:**

```sql
1.5707963267948966
```

**示例-4 :**

使用带有变量的 ACOS()函数并获取指定浮点值“0.45”的反余弦值。

```sql
DECLARE @Parameter_Value float;
SET @Parameter_Value = 0.45;
SELECT ACOS(@Parameter_Value);
```

**输出:**

```sql
1.1040309877476002
```

**应用:**

该函数用于返回指定值的反余弦或反余弦。