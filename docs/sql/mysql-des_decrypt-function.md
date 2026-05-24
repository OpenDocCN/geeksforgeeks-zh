# MySQL | DES_DECRYPT()函数

> 原文:[https://www.geeksforgeeks.org/mysql-des_decrypt-function/](https://www.geeksforgeeks.org/mysql-des_decrypt-function/)

MySQL**DES _ DECRYTE**函数用于使用 DES(数据加密标准)算法解密加密字符串。函数的作用是:用一个密钥来解密一个字符串。

DES _ DECRYPT 函数返回的值是一个解密字符串或空值。DES _ DECRYPT 函数接受两个参数，即加密字符串和解密字符串的密钥字符串。

**语法:**

```sql
DES_DECRYPT(encrypted_string, key_string);
```

**使用的参数:**

*   **encrypted _ string–**用于指定要解密的加密字符串。
*   **key _ string–**用于指定用于解密加密字符串的密钥。

**返回值:**
MySQL 中的 DES_DECRYPT 函数返回一个解密后的字符串。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1

**示例-1:** 在字符串上实现 DES_DECRYPT 函数。

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
AES_DECRYPT(AES_ENCRYPT('Geeksforgeeks', 'key_string'), 'key_string'); 
```

**输出:**

```sql
Geeksforgeeks 
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