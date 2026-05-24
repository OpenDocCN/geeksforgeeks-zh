# SQL Server 中的 NCHAR()函数

> 原文:[https://www.geeksforgeeks.org/nchar-function-in-sql-server/](https://www.geeksforgeeks.org/nchar-function-in-sql-server/)

**NCHAR()函数:**
SQL Server 中的这个函数用来返回基于数字代码的 Unicode 字符。
**例如**，如果指定的数字是 65，则该功能将返回 **A** 。

**特征:**

*   该函数用于查找给定数字的 Unicode 字符。
*   这个函数只接受正数。
*   该函数也接受十进制数，但在十进制符号之前返回数字代码的输出。
*   这个函数总是返回一个字符。
*   这里，数字代码从 65 开始。

**语法:**

```sql
NCHAR(number_code)
```

**参数:**
该方法接受单个参数，如下所示:

*   **number_code :** 以 Unicode 标准格式指定的数字代码，以便返回的字符。

**返回:**
返回基于数字代码的 Unicode 字符。

**示例-1 :**
获取数字代码 65 的 Unicode 字符。

```sql
SELECT NCHAR(65) AS NumberCodeToUnicode;
```

**输出:**

```sql
A
```

这里，输出是数字代码从 65 开始的第一个字符。

**示例-2 :**
获取指定十进制数 70.76 的 Unicode 字符。

```sql
SELECT NCHAR(70.76) AS NumberCodeToUnicode;
```

**输出:**

```sql
F
```

这里只考虑数字代码 70，忽略小数点后的数字。

**示例-3 :**
使用带有变量的 NCHAR()函数，获取指定数字代码 99 的 Unicode 字符。

```sql
DECLARE @number_code INT;  
SET @number_code = 99;  
SELECT NCHAR(@number_code);
```

**输出:**

```sql
c
```

**例-4 :**
得到 Unicode 字符 125，这是“250/2”的结果。

```sql
SELECT NCHAR(250/2);
```

**输出:**

```sql
}
```

**示例-5 :**
使用带有变量的 NCHAR()函数，获取指定浮点值“100.56”的 Unicode 字符。

```sql
DECLARE @number_code Float;  
SET @number_code = 100.56;  
SELECT NCHAR(@number_code);
```

**输出:**

```sql
d
```

**应用:**
该函数用于返回指定数字代码的 Unicode 字符，该字符为正数。