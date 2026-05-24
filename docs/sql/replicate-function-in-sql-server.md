# 在 SQL Server 中复制()函数

> 原文:[https://www . geesforgeks . org/replicate-function-in-SQL-server/](https://www.geeksforgeeks.org/replicate-function-in-sql-server/)

**REPLICATE()函数:**
SQL Server 中的这个函数用于给定次数重复指定的字符串。

**特征:**

*   该函数用于返回给定次数的指定字符串。
*   这个函数只接受字符串和整数作为参数。
*   如果没有提供第二个参数，此函数将返回一个错误。
*   这里返回的重复字符串在前一个字符串和后一个字符串之间没有空格。

**语法:**

```sql
REPLICATE(string, integer)
```

**参数:**
该方法接受如下两个参数:

*   **字符串:**要重复的指定字符串。
*   **整数:**字符串重复的指定次数。

**返回:**
返回指定次数的指定字符串。

**示例-1 :**
获取指定次数的指定字符串。

```sql
SELECT REPLICATE('Geeks for Geeks ', 2);
```

**输出:**

```sql
Geeks for Geeks Geeks for Geeks
```

**示例-2 :**
使用带有变量的 REPLICATE()函数，获取指定次数的重复字符串。

```sql
DECLARE @string VARCHAR(4);  
SET @string = '123 ';  
SELECT REPLICATE(@string, 4);

```

**输出:**

```sql
123 123 123 123
```

**示例-3 :**
使用带有两个变量的 REPLICATE()函数，获取指定次数的重复字符串。

```sql
DECLARE @string VARCHAR(6);  
DECLARE @int INT;  
SET @string = 'Geeks ';  
SET @int = 5;
SELECT REPLICATE(@string, @int);

```

**输出:**

```sql
Geeks Geeks Geeks Geeks Geeks
```

**示例-4 :**
获取指定次数的指定字符串，该字符串为浮点值。

```sql
SELECT REPLICATE('gfg ', 5.9);
```

**输出:**

```sql
gfg gfg gfg gfg gfg
```

**应用:**
该函数用于重复指定的字符串指定的次数。