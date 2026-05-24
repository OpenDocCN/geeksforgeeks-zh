# MySQL | DES_ENCRYPT()函数

> 原文:[https://www.geeksforgeeks.org/mysql-des_encrypt-function/](https://www.geeksforgeeks.org/mysql-des_encrypt-function/)

MySQL **DES_ENCRYPT** 函数用于使用 DES(数据加密标准)算法加密字符串。MySQL DES _ ENCRYPT 函数使用密钥加密字符串。

DES _ ENCRYPT 函数返回的值是加密字符串或空值。DES _ ENCRYPT 函数接受三个参数，即纯文本字符串和一个密钥字符串以及一个密钥号来加密该字符串。

**语法:**

```sql
DES_ENCRYPT(plaintext_string, [key_number | key_string]);
```

**使用的参数:**

*   **明文 _ 字符串–**用于指定要加密的字符串。
*   **key _ number–**用于从 DES 密钥文件中指定 0 到 9 范围内的数字。
*   **key _ string–**用于指定用于加密纯文本字符串的字符串。

**返回值:**
MySQL 中的 DES_ENCRYPT 函数返回一个加密字符串。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1

**示例-1:** 仅通过传递密钥号参数在字符串上实现 DES_ENCRYPT 函数。

```sql
SELECT 
DES_ENCRYPT('geeksforgeeks', 5); 
```

**输出:**

```sql
??p4???c????-? 
```

**示例-2:** 通过传递密钥号和密钥字符串参数，在字符串上实现 DES_ENCRYPT 函数。

```sql
SELECT 
DES_ENCRYPT('geeksforgeeks', 7), 
DES_ENCRYPT('geeksforgeeks', 'TestPassward'); 
```

**输出:**

```sql
??p4???c????-?    ??]?? ???{?}\\?t? 
```

**示例-3:** 在空字符串上实现 DES_ENCRYPT 函数。

```sql
SELECT 
DES_ENCRYPT(NULL, 7); 
```

**输出:**

```sql
NULL 
```