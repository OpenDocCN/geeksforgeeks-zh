# SQL Server 中的 LTRIM()函数

> 原文:[https://www.geeksforgeeks.org/ltrim-function-in-sql-server/](https://www.geeksforgeeks.org/ltrim-function-in-sql-server/)

LTRIM()函数有助于返回删除字符串左侧的所有空格字符。

**语法:**

```sql
LTRIM(string, [trim_string])
```

**参数:**

*   **字符串–**将删除前导空格字符的字符串。
*   **trim _ string–**它是一个可选参数，指定要从给定字符串中删除的字符。

**返回:**
该函数将在删除所有左侧空格字符后返回字符串。

**适用于以下版本的 [SQL Server](https://www.geeksforgeeks.org/tag/sql-server/) :**

*   SQL Server 2017
*   SQL Server 2016
*   SQL Server 2014
*   SQL Server 2012
*   2008
*   SQL Server 2008
*   SQL Server 2005

**例 1:**
LTRIM()函数的基本用法。

```sql
SELECT LTRIM('       GeeksforGeeks');
```

**输出:**

```sql
GeeksforGeeks
```

**示例 2 :**
使用带有变量的 LTRIM()函数。

```sql
DECLARE @str VARCHAR(50)
SET @str = '     Have a nice time ahead!!'
SELECT LTRIM(@str);
```

**输出:**

```sql
Have a nice time ahead!!
```

**示例-3 :**
在 LTRIM()函数中使用“trim_space”。

```sql
SELECT LTRIM (‘000325400’, ‘0’);
```

**输出:**

```sql
325400
```