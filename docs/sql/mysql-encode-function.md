# MySQL | ENCODE()函数

> 原文:[https://www.geeksforgeeks.org/mysql-encode-function/](https://www.geeksforgeeks.org/mysql-encode-function/)

MySQL **ENCODE()** 函数用于对纯文本字符串进行编码。MySQL ENCODE()函数返回一个二进制字符串，其大小与纯文本字符串相同。如果传递的字符串是空字符串，MySQL DECODE()函数将返回空字符串。

ENCODE()函数接受两个参数，即要编码的字符串和对纯文本字符串进行编码的密钥字符串。

**语法:**

```sql
ENCODE(plain_string, password_string);
```

**使用的参数:**

*   **纯文本字符串–**用于指定要编码的纯文本。
*   **password _ string–**用于指定对纯文本字符串进行编码的密码字符串。

**返回值:**
MySQL 中的 ENCODE 函数在编码后返回一个二进制字符串。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1

**示例-1:** 在字符串上实现 ENCODE 函数。

```sql
SELECT  
ENCODE('geeksforgeeks', 'passwordstring'); 
```

**输出:**

```sql
Q)?P????j[K 
```

**示例-2:** 对包含字符和整数的字符串实现 ENCODE 函数。

```sql
SELECT  
ENCODE('geeksforgeeks123', 'passwordstring'); 
```

**输出:**

```sql
Q)?P????j[K??= 
```

**示例-3:** 在空字符串上实现 ENCODE 函数。

```sql
SELECT  
ENCODE('NULL', 'passwordstring'); 
```

**输出:**

```sql
NULL 
```