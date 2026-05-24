# MySQL | SESSION_USER()函数

> 原文:[https://www.geeksforgeeks.org/mysql-session_user-function/](https://www.geeksforgeeks.org/mysql-session_user-function/)

MySQL **SESSION_USER()** 函数用于返回用户正在使用的 MySQL 连接的当前用户名和主机名。SESSION_USER()函数不需要传递任何参数。

SESSION_USER()函数返回的用户名是连接到服务器时用户指定的名称，而 SESSION_USER()函数返回的主机名是用户用来建立连接的客户端主机的名称。

**语法:**

```sql
SESSION_USER()
```

**使用的参数:**
不需要传递任何参数或参数。

**返回值:**
MySQL SESSION _ USER()函数返回 MySQL 连接的当前用户名和主机名。

**支持的 MySQL 版本**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1
*   MySQL 4.0
*   MySQL 3.23

**示例:**在 MySQL 中实现 SESSION_USER()函数。

```sql
SELECT SESSION_USER(); 
```

**输出:**

```sql
author@gfg 
```