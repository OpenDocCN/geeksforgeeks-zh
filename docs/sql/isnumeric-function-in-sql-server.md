# SQL Server 中的 ISNUMERIC()函数

> 原文:[https://www . geesforgeks . org/is numeric-function-in-SQL-server/](https://www.geeksforgeeks.org/isnumeric-function-in-sql-server/)

**ISNUMERIC()函数:**
SQL Server 中的这个函数用于检查所述表达式是否为数字。

**特征:**

*   该函数用于检查给定的表达式是否为数字。
*   如果给定的表达式是数字形式，此函数返回 1。
*   如果给定的表达式不是数字，此函数返回 0。
*   该功能属于高级功能。
*   这个函数只接受一个参数，即表达式。

**语法:**

```sql
ISNUMERIC(expression)

```

**参数:**
该方法只接受一个参数，如下所示:

*   **表达式:**指定的表达式或要检查其数值的值。

**返回:**
如果指定值是数字形式，则返回 1，否则返回 0。

**示例-1 :**
使用 ISNUMERIC()函数并获取输出。

```sql
SELECT ISNUMERIC(1352);

```

**输出:**

```sql
1
```

这里，返回 1，因为所述值是数字。

**示例-2 :**
使用 ISNUMERIC()函数并获取输出。

```sql
SELECT ISNUMERIC('abd');

```

**输出:**

```sql
0
```

这里，0 作为输出返回，因为所述表达式不是数字。

**示例-3 :**
使用 ISNUMERIC()函数并使用变量获取输出。

```sql
DECLARE @exp INT;
SET @exp = 44;
SELECT ISNUMERIC(@exp);

```

**输出:**

```sql
1
```

**示例-4 :**
使用 ISNUMERIC()函数，并使用乘法运算和变量获得输出。

```sql
DECLARE @exp INT;
SET @exp = 30*7;
SELECT ISNUMERIC(@exp);

```

**输出:**

```sql
1
```

**应用:**
此功能用于测试所述表达式是否为数字。