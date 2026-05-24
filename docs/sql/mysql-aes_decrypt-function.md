# MySQL | AES_DECRYPT()函数

> 原文:[https://www.geeksforgeeks.org/mysql-aes_decrypt-function/](https://www.geeksforgeeks.org/mysql-aes_decrypt-function/)

函数的作用是:解密一个加密的字符串后，返回原始的字符串。它使用 AES(高级加密标准)算法执行解密。函数的作用是:如果检测到无效数据，则返回解密后的字符串或空值。

AES_DECRYPT 函数返回的值是使用 AES_ENCRYPT 函数加密的原始明文字符串。函数接受两个参数，即加密字符串和用于解密加密字符串的字符串。

**语法:**

```sql
AES_DECRYPT(encrypted_string, key_string)
```

**使用的参数:**

*   **encrypted _ string–**用于指定加密字符串。
*   **密钥 _ 字符串–**用于指定用于解密加密 _ 字符串的字符串。

**返回值:**
MySQL 中的 AES_DECRYPT 函数返回使用 AES_ENCRYPT 函数加密的原始明文字符串。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1

**示例-1:** 在字符串上实现 AES_DECRYPT 函数。

```sql
SELECT  
AES_DECRYPT(AES_ENCRYPT('ABC', 'key_string'), 'key_string'); 
```

**输出:**

```sql
ABC 
```

**示例-2:** 对包含字符和整数值的字符串实现 AES_DECRYPT 函数。

```sql
SELECT  
AES_DECRYPT(AES_ENCRYPT('ABC123', 'key_string'), 'key_string'); 
```

**输出:**

```sql
ABC123 
```

**示例-3:** 在更大的字符串上实现 AES_DECRYPT 函数。

```sql
SELECT  
AES_DECRYPT(AES_ENCRYPT('geeksforgeeks', 'key_string'), 'key_string'); 
```

**输出:**

```sql
geeksforgeeks 
```

**示例-4:** 在空字符串上实现 AES_DECRYPT 函数。

```sql
SELECT  
AES_DECRYPT(AES_ENCRYPT(NULL, 'key_string'), 'key_string'); 
```

**输出:**

```sql
NULL  
```