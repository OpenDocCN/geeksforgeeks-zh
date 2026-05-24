# MySQL | MD5 函数

> 原文:[https://www.geeksforgeeks.org/mysql-md5-function/](https://www.geeksforgeeks.org/mysql-md5-function/)

MySQL MD5 函数用于返回字符串的 MD5 128 位校验和表示。MD5 消息摘要算法是一种广泛使用的哈希函数，可产生 128 位哈希值。MD5 函数返回的值是由 32 个十六进制数字组成的二进制字符串，如果参数为空，则返回空值。

返回值也可以用作哈希键。MD5 函数接受一个参数，即要加密的字符串。

**语法:**

```sql
MD5( plain_string )
```

**使用的参数:**

*   **纯文本字符串–**用于指定要加密的纯文本字符串。

**返回值:**
MySQL 中的 MD5 函数返回一个由 32 个十六进制数字组成的二进制字符串。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1

**示例-1:** 在字符串上实现 MD5 函数。

```sql
SELECT 
MD5('xyz'); 
```

**输出:**

```sql
d16fb36f0911f878998c136191af705e 
```

**示例-2:** 对包含字符和整数值的字符串实现 MD5 函数。

```sql
SELECT 
MD5('xyz123'); 
```

**输出:**

```sql
j89hj65l0355k878998c136191kl906w 
```

**示例-3:** 在更大的字符串上实现 MD5 函数。

```sql
SELECT 
MD5('geeksforgeeks'); 
```

**输出:**

```sql
a6eb56f80be8a120436d6f1c9b8d87ca 
```

**示例-4:** 在空字符串上实现 MD5 函数。

```sql
SELECT 
MD5('NULL'); 
```

**输出:**

```sql
NULL 
```