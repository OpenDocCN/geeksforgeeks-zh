# SQL | ENCRYPT 函数

> 原文:[https://www.geeksforgeeks.org/sql-encrypt-function/](https://www.geeksforgeeks.org/sql-encrypt-function/)

SQL Encrypt 函数用于使用 UNIX crypt()加密字符串。该函数基于 Unix crypt()系统调用，因此在 Windows 系统上返回空值。加密函数接受两个参数，即要加密的字符串和盐。
加密函数返回一个二进制字符串。

**语法:**

```sql
ENCRYPT(string, salt)
```

**使用的参数:**

*   **字符串–**用于指定要使用 UNIX crypt()加密的纯文本字符串。
*   **salt–**用于指定长度至少为 2 个字符的字符串，可以在加密过程中使用。如果没有提供 salt，ENCRYPT 函数将使用一个随机值。

**返回值:**
SQL 中的 Encrypt 函数返回一个二进制字符串。

在下列情况下，加密函数返回空值:

*   如果 salt 长度少于 2 个字符，则加密函数返回空值。
*   如果字符串为空，则加密函数返回空值。
*   如果 UNIX crypt()在系统上不可用，则加密函数返回空值。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1

**示例-1:** 在字符串上实现加密功能。

```sql
SELECT 
ENCRYPT('xyz'); 
```

**输出:**

```sql
sf3Le/pz2ApNY 
```

**示例-2:** 在更大的字符串上实现加密功能。

```sql
SELECT 
ENCRYPT('geeksforgeeks'); 
```

**输出:**

```sql
.mblNS3yOZxb2 
```

**示例-3:** 通过传递两个参数在字符串上实现加密功能。

```sql
SELECT 
ENCRYPT('geeksforgeeks', '123'); 
```

**输出:**

```sql
12SrVMQf0pwFU 
```

**示例-4:** 通过在 salt 参数中传递少于 2 个字符，在字符串上实现 Encrypt 函数。

```sql
SELECT 
ENCRYPT('geeksforgeeks', '2'); 
```

**输出:**

```sql
NULL 
```

由于 salt 参数的长度小于 2 个字符，因此 Encrypt 函数返回空值。

**示例-5:** 在空字符串上实现加密功能。

```sql
SELECT 
ENCRYPT(NULL); 
```

**输出:**

```sql
NULL 
```