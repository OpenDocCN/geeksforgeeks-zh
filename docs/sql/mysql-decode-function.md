# MySQL | DECODE()函数

> 原文:[https://www.geeksforgeeks.org/mysql-decode-function/](https://www.geeksforgeeks.org/mysql-decode-function/)

MySQL **DECODE()** 函数用于解码编码字符串并返回原始字符串。如果编码字符串为空字符串，MySQL DECODE()函数将返回空字符串。

DECODE()函数接受两个参数，即要解码的编码字符串和解码编码字符串的密码字符串。

**语法:**

```sql
DECODE(encoded_string, password_string);
```

**使用的参数:**

*   **encoded _ string–**用于指定待解码的编码字符串。
*   **password _ string–**用于指定对编码字符串进行解码的密码字符串。

**返回值:**
MySQL 中的 DECODE 函数对编码后的字符串进行解码后返回原始字符串。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1

**示例-1:** 在字符串上实现 DECODE 函数。

```sql
SELECT  
DECODE(ENCODE('geeksforgeeks', 'passwordstring'), 'passwordstring'); 
```

**输出:**

```sql
geeksforgeeks 
```

**示例-2:** 对包含字符和整数的字符串实现 DECODE 函数。

```sql
SELECT  
DECODE(ENCODE('geeksforgeeks123', 'passwordstring'), 'passwordstring'); 
```

**输出:**

```sql
geeksforgeeks123 
```

**示例-3:** 对空字符串实现 DECODE 函数，压缩后返回字符串长度。

```sql
SELECT  
DECODE(ENCODE('NULL', 'passwordstring'), 'passwordstring'); 
```

**输出:**

```sql
NULL 
```