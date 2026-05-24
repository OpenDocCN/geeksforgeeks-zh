# SQL Server 中的 `TRIM()` 函数

> 原文: [https://www.geeksforgeeks.org/trim-function-in-sql-server/](https://www.geeksforgeeks.org/trim-function-in-sql-server/)

## `TRIM()` 功能

SQL Server 中的此函数用于从指定字符串的开头或结尾省略空格字符或其他指定字符。

*   此函数用于从字符串的开头或结尾省略空格字符或其他给定的字符。
*   此函数接受特定的字符和字符串。
*   默认情况下，此函数可以省略给定字符串的首尾空格。

## 语法

```sql
TRIM([characters FROM ]string)
```

## 参数

该方法接受两个参数。

*   `characters from` – 要省略的特定字符。
*   `string` - 要省略字符或空格的指定字符串。

## 返回

它在省略空格字符或开头或结尾的一些附加字符后返回指定的字符串。

## 示例-1

在省略指定字符串的开始和结束空格后获取该字符串。

```sql
SELECT TRIM('     GFG     ');
```

**输出:**

```sql
GFG
```

## 示例-2

使用带有变量的 `TRIM()` 函数，并获取修改后的指定字符串作为输出。

```sql
DECLARE @str VARCHAR(10);
SET @str = '   Geeks   ';
SELECT TRIM(@str);
```

**输出:**

```sql
Geeks
```

## 示例-3

在省略特定字符及其开始和结束空格后获取指定字符串。

```sql
SELECT TRIM('@$ ' FROM '    @geeksforgeeks$    ');
```

**输出:**

```sql
geeksforgeeks
```

这里，指定的字符也被省略。

## 示例-4

使用带有两个变量的 `TRIM()` 函数，并获取修改后的指定字符串作为输出。

```sql
DECLARE @str VARCHAR(10);
DECLARE @char VARCHAR(10);
SET @str = '   &Geeks*  ';
SET @char = '&* ';
SELECT TRIM(@char FROM @str);
```

**输出:**

```sql
Geeks
```

## 应用

此函数用于在给定字符串的开头或结尾省略空格字符或其他指定字符后返回修改后的字符串。