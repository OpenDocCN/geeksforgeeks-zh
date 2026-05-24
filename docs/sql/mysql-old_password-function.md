# MySQL | OLD_PASSWORD 功能

> 原文:[https://www.geeksforgeeks.org/mysql-old_password-function/](https://www.geeksforgeeks.org/mysql-old_password-function/)

MySQL **OLD_PASSWORD** 函数用于根据明文密码字符串生成散列密码。OLD_PASSWORD 函数使用哈希技术来生成哈希密码。该功能由认证系统执行。

MySQL 服务器使用该函数来加密 MySQL 密码，以便存储在用户授权表的密码列中。OLD_PASSWORD 函数返回的值是一个散列字符串，如果参数为空，则返回空值。OLD_PASSWORD 函数接受一个参数，即要加密的字符串。

**语法:**

```sql
OLD_PASSWORD( plain_string )
```

**使用的参数:**

*   **纯文本字符串–**用于指定要加密的纯文本字符串。

**返回值:**
MySQL 中的 OLD_PASSWORD 函数返回一个散列字符串。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1

**示例-1:** 在字符串上实现 OLD_PASSWORD 函数。

```sql
SELECT 
OLD_PASSWORD('xyz'); 
```

**输出:**

```sql
5re6hsuy7dsvgs25 
```

**示例-2:** 在包含字符和整数值的字符串上实现 OLD_PASSWORD。

```sql
SELECT 
OLD_PASSWORD('xyz123'); 
```

**输出:**

```sql
56fsrfshg312nsh34wf51 
```

**示例-3:** 在更大的字符串上实现 OLD_PASSWORD 函数。

```sql
SELECT 
OLD_PASSWORD('geeksforgeeks'); 
```

**输出:**

```sql
98dsygdy5syg43gs21 
```

**示例-4:** 在空字符串上实现 OLD_PASSWORD 函数。

```sql
SELECT 
OLD_PASSWORD('NULL'); 
```

**输出:**

```sql
NULL 
```