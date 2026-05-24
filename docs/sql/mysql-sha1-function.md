# MySQL | SHA1()功能

> 原文:[https://www.geeksforgeeks.org/mysql-sha1-function/](https://www.geeksforgeeks.org/mysql-sha1-function/)

MySQL **SHA1()** 函数用于使用 SHA-1 技术加密字符串。 [SHA1](https://www.geeksforgeeks.org/sha-1-hash-in-java/) 代表安全散列算法，它为用户输入的字符串生成 160 位校验和。

如果作为参数传递的字符串是空字符串，MySQL SHA1()函数将返回空值。SHA1()函数接受一个参数，即要加密的字符串。

**语法:**

```sql
SHA1(string)
```

**使用的参数:**

**字符串–**用于指定要加密的纯文本字符串。

**返回值:**
MySQL 中的 SHA1()函数返回加密字符串，如果传递的字符串为空字符串，则返回 NULL。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1

**示例-1:** 在字符串上实现 SHA1()函数。

```sql
SELECT  
SHA1('geeksforgeeks'); 
```

**输出:**

```sql
69c9a5c19c5c27e43cb0efc4c8644ed6d03a110b 
```

**示例-2:** 在包含字符和整数的字符串上实现 SHA1()函数。

```sql
SELECT 
SHA1('geeksforgeeks123'); 
```

**输出:**

```sql
53ce00666cbef425ab8d06ed652095bea20a1616 
```

**示例-3:** 对空字符串实现 SHA1()函数，并在压缩后返回字符串的长度。

```sql
SELECT  
SHA1(NULL); 
```

**输出:**

```sql
NULL 
```