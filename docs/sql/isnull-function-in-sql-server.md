# SQL Server 中的 ISNULL()函数

> 原文:[https://www . geesforgeks . org/is null-function-in-SQL-server/](https://www.geeksforgeeks.org/isnull-function-in-sql-server/)

is null():

SQL Server 中的这个函数用于返回给定的值，以防所述表达式为空。此外，如果给定的表达式不是空的，那么它将返回指定的表达式。

**特征:**

*   如果给定的表达式为空，该函数用于查找给定值。
*   该函数用于查找给定的表达式，以防给定的表达式不为空。
*   该功能属于高级功能。
*   这个函数接受两个参数，即表达式和值。

**语法:**

```sql
ISNULL(expression, value)
```

**参数:**

此方法接受两个参数。

*   **表达式–**
    要检查是否为空的指定表达式。
*   **值–**
    表达式为空时返回的指定值。

**返回:**

它返回给定的值，如果指定的表达式为空，否则它返回指定的表达式，如果给定的表达式不为空。

**示例-1 :**

使用 ISNULL()函数并获取输出。

```sql
SELECT ISNULL('gfg', 'Geeks');
```

**输出:**

```sql
gfg
```

这里，返回表达式，因为给定值不为空。

**示例-2 :**

使用 ISNULL()函数并获取输出。

```sql
SELECT ISNULL(NULL, 'Geeks');
```

**输出:**

```sql
Geeks
```

这里，表达式为空，所以指定的值作为输出返回。

**示例-3 :**

使用 ISNULL()函数并使用变量获取输出。

```sql
DECLARE @exp VARCHAR(50);
SET @exp = 'geeksforgeeks';
SELECT ISNULL(@exp, 150);
```

**输出:**

```sql
geeksforgeeks
```

**示例-4 :**

使用 ISNULL()函数，并使用变量获取输出。

```sql
DECLARE @exp VARCHAR(50);
DECLARE @val VARCHAR(50);
SET @exp = NULL;
SET @val = 'GFG';
SELECT ISNULL(@exp, @val);
```

**输出:**

```sql
GFG
```

**应用:**

该函数用于查找给定值，如果指定表达式为空，则查找指定表达式，如果给定表达式不为空，则查找指定表达式。