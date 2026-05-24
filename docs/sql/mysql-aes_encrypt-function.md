# MySQL | AES_ENCRYPT()函数

> 原文:[https://www.geeksforgeeks.org/mysql-aes_encrypt-function/](https://www.geeksforgeeks.org/mysql-aes_encrypt-function/)

MySQL **AES_ENCRYPT** 函数用于使用[高级加密标准(AES)](https://www.geeksforgeeks.org/difference-between-aes-and-des-ciphers/) 算法加密字符串。MySQL AES _ ENCRYPT 函数用 128 位密钥长度编码数据，但它可以扩展到 256 位密钥长度。它加密一个字符串并返回一个二进制字符串。

AES_ENCRYPT 函数返回的值是二进制字符串，如果参数为空，则返回空值。AES_ENCRYPT 函数接受两个参数，即加密字符串和用于加密字符串的密钥字符串。

**语法:**

```sql
AES_ENCRYPT(str, key_str)
```

**使用的参数:**

*   **字符串–**用于指定普通字符串。
*   **key _ str–**用于指定用于加密字符串的字符串。

**返回值:**
MySQL 中的 AES_ENCRYPT 函数返回一个二进制字符串。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1

**示例-1:** 在字符串上实现 AES_ENCRYPT 函数。

```sql
SELECT
AES_ENCRYPT('ABC', 'key'); 
```

**输出:**

```sql
\\YJ??f&K?M?q?* 
```

**示例-2:** 在更大的字符串上实现 AES_ENCRYPT 函数。

```sql
SELECT 
AES_ENCRYPT('geeksforgeeks', 'key'); 
```

**输出:**

```sql
2G???B?????*?? 
```

**示例-3:** 在空字符串上实现 AES_ENCRYPT 函数。

```sql
SELECT  
(AES_ENCRYPT(NULL, 'key'); 
```

**输出:**

```sql
NULL 
```