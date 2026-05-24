# MySQL | PASSWORD 功能

> 原文:[https://www.geeksforgeeks.org/mysql-password-function/](https://www.geeksforgeeks.org/mysql-password-function/)

MySQL PASSWORD 函数用于使用纯文本密码字符串生成哈希密码。它使用哈希技术生成哈希密码。该功能由认证系统执行。

MySQL 服务器使用 Password 函数加密 MySQL 密码，以存储在用户授权表的 PASSWORD 列中。PASSWORD 函数返回的值是哈希字符串，如果参数为空，则返回空值。PASSWORD 函数接受一个参数，即要加密的字符串。

**语法:**

```sql
PASSWORD( string_to_encrypt )
```

**使用的参数:**

*   **string _ to _ encrypt–**用于指定要加密的纯文本字符串。

**返回值:**
MySQL 中的 PASSWORD 函数返回一个散列字符串。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1

**示例-1:** 在字符串上实现 PASSWORD 函数。

```sql
SELECT 
PASSWORD('xyz'); 
```

**输出:**

```sql
6gd7gb67shy87865 
```

**示例-2:** 对包含字符和整数值的字符串实现 PASSWORD 函数。

```sql
SELECT 
PASSWORD('xyz123'); 
```

**输出:**

```sql
54fg56gs32sgi3862 
```

**示例-3:** 在更大的字符串上实现 PASSWORD 函数。

```sql
SELECT 
PASSWORD('geeksforgeeks'); 
```

**输出:**

```sql
79sgs54uksr1fy76509 
```

**示例-4:** 在空字符串上实现 PASSWORD 函数。

```sql
SELECT 
PASSWORD('NULL'); 
```

**输出:**

```sql
NULL 
```