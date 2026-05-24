# MySQL | UNCOMPRESSED_LENGTH()函数

> 原文:[https://www . geesforgeks . org/MySQL-uncompressed _ length-function/](https://www.geeksforgeeks.org/mysql-uncompressed_length-function/)

函数的作用是:返回字符串被压缩前的长度。它用于已使用 COMPLATED()函数压缩的字符串。

函数的作用是:如果压缩后的字符串为空字符串，则返回空值。它接受一个参数，即需要计算长度的压缩字符串。

**语法:**

```sql
UNCOMPRESSED_LENGTH(compressed_string);
```

**使用的参数:**
**compressed _ string–**用于指定需要计算长度的压缩字符串。

**返回值:**
MySQL 中的 UNCOMPRESSED_LENGTH()函数返回压缩字符串的长度。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1

**示例-1:** 在字符串上实现 UNCOMPRESSED_LENGTH()函数。

```sql
SELECT  
UNCOMPRESSED_LENGTH(COMPRESS('geeksforgeeks')); 
```

**输出:**

```sql
13 
```

**示例-2:** 在包含字符和整数的字符串上实现 UNCOMPRESSED_LENGTH()函数。

```sql
SELECT 
UNCOMPRESSED_LENGTH(COMPRESS('geeksforgeeks123')); 
```

**输出:**

```sql
16 
```

**示例-3:** 对空字符串实现 UNCOMPRESSED_LENGTH()函数，并返回压缩后的字符串长度。

```sql
SELECT
UNCOMPRESSED_LENGTH(COMPRESS(NULL)); 
```

**输出:**

```sql
NULL 
```