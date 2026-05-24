# MySQL | VERSION()函数

> 原文:[https://www.geeksforgeeks.org/mysql-version-function/](https://www.geeksforgeeks.org/mysql-version-function/)

MySQL **Version()** 函数用于返回 MySQL 数据库的当前版本。该函数使用 utf8 字符集。一般在版本号后面有一个后缀返回。Version()函数不需要传递任何参数。

**语法:**

```sql
VERSION()
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

**示例:**在 MySQL 中实现 Version()函数。

```sql
SELECT VERSION(); 
```

**输出:**

```sql
5.7.26-0ubuntu0.18.04.1 
```