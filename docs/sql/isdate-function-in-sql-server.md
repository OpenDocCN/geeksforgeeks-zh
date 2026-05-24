# SQL Server 中的 ISDATE()函数

> 原文:[https://www . geesforgeks . org/is date-function-in-SQL-server/](https://www.geeksforgeeks.org/isdate-function-in-sql-server/)

**ISDATE()函数:**
SQL Server 中的这个[函数用于检查指定的表达式是否为有效日期。](https://www.geeksforgeeks.org/tag/sql-server/)

**特征:**

*   该功能用于查找规定日期是否有效。
*   该功能属于日期功能。
*   这个函数只接受一个参数，即一个表达式。
*   该功能还可以包括带有规定日期的时间。
*   该函数可以返回 1 或 0。

**语法:**

```sql
ISDATE(expression)
```

**参数:**
该方法只接受一个参数，如下所示。

*   **表达式–**要检查的指定表达式。

**返回:**
如果所述表达式是有效日期，则返回 1，否则返回 0。

**示例-1 :**
使用 ISDATE()函数并获取输出。

```sql
SELECT ISDATE('2020/01/03');
```

**输出:**

```sql
1
```

**示例-2 :**
使用带有变量的 ISDATE()函数并获得所需的输出。

```sql
DECLARE @exp VARCHAR(50);
SET @exp= '2021/12/25';
SELECT ISDATE(@exp);

```

**输出:**

```sql
1
```

**示例-3 :**
使用 ISDATE()函数，以日期为参数，其中还包括时间。

```sql
SELECT ISDATE('2021/01/03 08:55');
```

**输出:**

```sql
1
```

**示例-4 :**
使用带有无效日期的 ISDATE()函数并获取输出。

```sql
SELECT ISDATE('2021/01/32 08:55');
```

**输出:**

```sql
0
```

**应用:**
该功能用于检查给定的表达式是否为有效日期。