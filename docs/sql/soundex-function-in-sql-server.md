# SQL Server 中的 SOUNDEX()函数

> 原文:[https://www . geesforgeks . org/soundex-function-in-SQL-server/](https://www.geeksforgeeks.org/soundex-function-in-sql-server/)

**SOUNDEX()函数:**
SQL Server 中的这个函数用来返回一个四个字符的代码，以便评估两个指定表达式的相似性。

**特征:**

*   该函数用于查找两个指定表达式的四字符代码。
*   此函数接受表达式。
*   表达式可以是常量、变量或列。
*   此函数将指定的表达式转换为四个字符的代码，该代码基于指定字符串在发音时的发音。

**语法:**

```sql
SOUNDEX(expression)
```

**参数:**
该方法只接受一个参数，如下所示:

*   **表达式:**要计算的指定表达式。它可以是常量、变量或列。

**返回:**
它返回一个四字符代码，以便评估两个给定表达式的相似性。

**示例-1 :**
获取听起来相似的指定表达式的四个字符代码。

```sql
SELECT SOUNDEX('see'), SOUNDEX('sea');
```

**输出:**

```sql
S000
```

**示例-2 :**
使用带有变量的 SOUNDEX()函数，得到一个四个字符的代码。

```sql
DECLARE @exp1 VARCHAR(15); 
DECLARE @exp2 VARCHAR(15);
SET @exp1 = 'sum';
SET @exp2 = 'some';
SELECT SOUNDEX(@exp1), SOUNDEX(@exp2);
```

**输出:**

```sql
S500
```

**示例-3 :**
获取一个听起来一点都不相似的指定表达式的四个字符代码。

```sql
SELECT SOUNDEX('cs'), SOUNDEX('portal');
```

**输出:**

```sql
P634
```

**示例-4 :**
获取指定表达式的四个字符的整数代码。

```sql
SELECT SOUNDEX(34), SOUNDEX(45);
```

**输出:**

```sql
0000
```

所以，这里不管整数是什么，生成的代码都会是“0000”。

**应用:**
该函数用于生成指定表达式的四个字符代码。