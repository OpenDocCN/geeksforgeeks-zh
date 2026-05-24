# SQL Server 中的 DATALENGTH()函数

> 原文:[https://www . geesforgeks . org/data length-function-in-SQL-server/](https://www.geeksforgeeks.org/datalength-function-in-sql-server/)

**DATALENGTH() :**
这个函数返回一个表达式的长度，表达式的长度将以字节为单位。

**语法:**

```sql
DATALENGTH( expression )  

```

*   **参数–**
    该方法接受如上所述的单参数，描述如下。
*   **表达式–**
    它是返回长度的数据类型的表达式。如果表达式为空，则返回空值。

**返回:**
返回用于表示表达式的字节数。

**示例-1 :**
返回表达式的长度。

```sql
SELECT DATALENGTH('Geeksforgeeks');

```

**输出:**

```sql
13

```

**示例-2 :**
检查 DATALENGTH()函数是否计算尾随空格。

```sql
SELECT DATALENGTH('GFG   ');

```

**输出:**

```sql
6

```

**示例-3 :**
检查 DATALENGTH()函数是否计算前导空格。

```sql
SELECT DATALENGTH('    GFG');

```

**输出:**

```sql
7

```

**示例-4 :**
DATALENGTH()函数返回 NULL，如果表达式为 NULL。

```sql
SELECT DATALENGTH(NULL);

```

**输出:**

```sql
NULL

```