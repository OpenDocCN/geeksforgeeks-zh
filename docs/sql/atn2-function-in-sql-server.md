# SQL Server 中的 ATN2()函数

> 原文:[https://www.geeksforgeeks.org/atn2-function-in-sql-server/](https://www.geeksforgeeks.org/atn2-function-in-sql-server/)

在本文中，我们将介绍 ATN2()函数，在该函数中，我们将看到如何获得两个给定数字的反正切。我们一个一个来讨论。

```sql
// here val1 and val2 are input.
Input  : ATN2(val1, val2)     
Output : Arc tangent result.

```

**ATN2() :**
是返回两个数的反正切的函数。

**语法:**

```sql
ATN2(val1, val2)

```

**参数:**
该方法接受上面提到的和下面描述的两个参数。

*   **val1、val2:**
    正是这两个数值来计算反正切。

**返回–**
返回两个数的反正切。

**例-1 :**
当自变量为正数时。

```sql
SELECT ATN2(2.53, 5.6);

```

**输出:**

```sql
0.42433793483800258

```

**例-2 :**
当自变量为负数时。

```sql
SELECT ATN2(-2.53, -5.6);

```

**输出:**

```sql
-2.7172547187517906

```

**示例-3 :**
当 PI()函数传递其中一个参数时。

```sql
SELECT ATN2(PI(), 4);

```

**输出:**

```sql
0.66577375002835382

```