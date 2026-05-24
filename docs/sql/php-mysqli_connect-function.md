# PHP | mysqli_connect()函数

> 原文:[https://www.geeksforgeeks.org/php-mysqli_connect-function/](https://www.geeksforgeeks.org/php-mysqli_connect-function/)

PHP 中的*MySQL _ connect()*函数是用来连接你和数据库的。在之前版本的连接中*使用了 mysql_connect()* 进行连接，然后出现了*MySQL _ connect()*其中 *i* 表示连接的改进版本，比 *mysql_connect()* 更安全。
**语法:**

```sql
mysqli_connect ( "host", "username", "password", "database_name" )
```

**使用的参数:**

*   ***主机*** **:** 可选，指定主机名或 IP 地址。在本地服务器的情况下，localhost 用作连接本地服务器和运行程序的通用关键字。
*   ***用户名*** **:** 可选，指定 mysql 用户名。在本地服务器用户名是*根。*
*   ***密码*** **:** 可选，指定 mysql 密码。
*   ***数据库 _ 名称*** **:** 是对数据进行操作的数据库名称。它也是可选的。

**返回值:**

*   它返回一个代表 MySql 连接的对象。如果连接失败，则返回假。

**程序:**下面是*MySQL _ connect()*功能的实现。

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```sql
<?php
    mysqli_connect("localhost", "root", "", "GFG");

    if(mysqli_connect_error())
        echo "Connection Error.";
    else
        echo "Database Connection Successfully.";
?>
```

输出:

```sql
Database Connection Successfully.
```