# SQL Server 中的 QUOTENAME()函数

> 原文:[https://www . geesforgeks . org/quote name-function-in-SQL-server/](https://www.geeksforgeeks.org/quotename-function-in-sql-server/)

**QUOTENAME()函数:**
SQL Server 中的这个函数用于返回一个添加了分隔符的 Unicode 字符串，以便使该字符串成为有效的 SQL Server 分隔标识符。

**特征:**

*   此函数用于查找添加了分隔符的 Unicode 字符串。
*   这个函数只接受字符串和分隔符。
*   如果未指定，此函数默认添加分隔符。
*   这个函数总是返回字符串和分隔符。

这里，字符串限制为 128。

**语法:**

```sql
QUOTENAME(string, quote_char)
```

**参数:**
该方法接受如下两个参数:

*   **字符串:**Unicode 字符数据的指定字符串，限制为 128 个字符。
*   **quote_char :** 可选。它是一个单字符字符串，用作分隔符。例如，它可以是单引号即( ' )，或左括号或右括号即([])，或双引号即( " )，或左括号或右括号即( () )，或大于号或小于号即(>)或左括号或右括号即({})或倒勾即(`)。此外，如果未指定此参数，则默认使用括号。

**返回:**
它返回一个添加了分隔符的 Unicode 字符串，以便使该字符串成为有效的 SQL Server 分隔标识符。

**示例-1 :**
获取字符串“xyz”的 Unicode 字符串。

```sql
SELECT QUOTENAME('xyz');
```

**输出:**

```sql
[xyz]
```

这里没有定义 quote_char 参数，但是默认情况下会在输出中添加括号。

**示例-2 :**
获取带括号分隔符的 Unicode 字符串。

```sql
SELECT QUOTENAME('abc', '{}');
```

**输出:**

```sql
{abc}
```

这里，分隔符在参数中指定，因此它们作为输出返回。

**示例-3 :**
使用带有变量的 QUOTENAME()函数，获取指定字符串的 Unicode 字符串。

```sql
DECLARE @string VARCHAR(3);  
SET @string = '123';  
SELECT QUOTENAME(@string);
```

**输出:**

```sql
[123]
```

**示例-4 :**
使用带有变量的 QUOTENAME()函数，获取指定字符串的 Unicode 字符串以及分隔符。

```sql
DECLARE @string VARCHAR(4);
DECLARE @delimiter VARCHAR(2);
SET @string = 'jk12';
SET @delimiter = '()';
SELECT QUOTENAME(@string, @delimiter);

```

**输出:**

```sql
(jk12)
```

**示例-5 :**
获取带大于号的 Unicode 字符串。

```sql
SELECT QUOTENAME('23', '>');
```

**输出:**

```sql
<23>
```

此分隔符仅适用于数字。

**应用程序:**
该函数用于返回添加了分隔符的 Unicode 字符串，以便使该字符串成为有效的 SQL Server 分隔标识符。