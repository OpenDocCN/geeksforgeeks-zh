# MySQL | USER()函数

> 原文:[https://www.geeksforgeeks.org/mysql-user-function/](https://www.geeksforgeeks.org/mysql-user-function/)

MySQL **USER()** 函数用于返回用户正在使用的 MySQL 连接的当前用户名和主机名。该函数使用 utf8 字符集。USER()函数不需要传递任何参数。

user()函数返回的用户名是连接到服务器时指定的用户名，而 USER()函数返回的主机名是用户用来建立连接的客户端主机的名称。用户()函数类似于会话用户()函数和系统用户()函数。

**语法:**

```sql
USER()
```

**使用的参数:**
不需要传递任何参数或参数。

**返回值:**
MySQL Version()函数以字符串形式返回 MySQL 数据库的版本。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1
*   MySQL 4.0
*   MySQL 3.23

**示例:**在 MySQL 中实现 USER()函数。

```sql
SELECT USER(); 
```

**输出:**

```sql
author@gfg 
```