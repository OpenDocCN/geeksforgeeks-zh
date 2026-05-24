# MySQL 程序功能

> 原文:[https://www.geeksforgeeks.org/mysqli-procedural-functions/](https://www.geeksforgeeks.org/mysqli-procedural-functions/)

**MySQL(MySQL enhanced)**为数据及其管理提供程序性和面向对象的接口。MySQL 函数的 I 扩展允许用户访问它的数据库服务器。MySQL 改进扩展是专门为 MySQL 4 . 1 . 13 版和新版本而设计的。
**使用准备好的报表的优势:**

1.  准备好的声明非常有效，特别是为了避免 SQL 注入攻击。
2.  准备好的语句被重复使用。它还减少了解析时间和开销，因为查询的准备只进行一次。
3.  数据库解析、编译、优化查询语句并存储结果。
4.  将参数与查询绑定可以最大限度地减少总带宽，因为参数是在需要时发送的，而不是发送整个查询。
5.  将参数与占位符绑定更安全、更容易，因为正确的格式化是自动完成的。
6.  通过将占位符值发送到 MySQL 服务器，它遵循客户机-服务器协议。
7.  它使用不同的变量集多次执行特定的查询语句，有效地降低了成本。
8.  它还节省了数据复制和转换。
9.  准备好的语句不太容易出错，因为语句首先被解析，然后被解析的值被服务器使用。

我们不能涵盖这个主题下的所有内容，但让我们看看 MySQLi 的一些重要过程函数
。
**1。MySQL _ connect():**
如您所知，在执行任何数据库相关操作之前，您需要建立与 MySQL 数据库服务器的连接。如果连接成功建立，则返回数据库连接资源标识符。如果连接失败，那么它只会抛出一个错误。

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```sql
<?php
// Database configuration
$host  = "localhost";
$dbuser = "root";
$dbpass = "";
$dbname = "GFG";

// Create database connection
mysqli_connect($host, $dbuser, $dbpass, $dbname);

// Check connection
if(mysqli_connect_error())
{
 echo "Connection establishing failed!";
}
else
{
 echo "Connection established successfully.";
}
?>
```

**输出:**

```sql
Connection established successfully. 
```

**2。MySQL _ connect _ error():**
当连接没有成功时，MySQL 函数会抛出一个错误，并且该函数会将该错误存储在之前对 MySQL _ connect()的调用中。如果没有遇到错误，它将返回空值。如果遇到任何错误，它将返回一条错误消息。
**注:**

*   要测试*MySQL _ connect _ error()*，在 XAMPP 控制面板中停止 MySQL 服务器，然后调用上面的带有 MySQL _ connect()的 PHP 代码。

*   如果在 PHP 配置中启用了 *display_errors* ，可以看到*MySQL _ connect _ error()*的一个错误，返回如下消息。

```sql
Connection failed as the target machine actively refused it. 
```

**注意:**
在良好的编程实践中，最好不要显示任何错误消息。出于故障排除的目的，使用*MySQL _ connect _ error()*记录以下代码中提到的错误。

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```sql
<?php
// Database configuration
$host  = "localhost";
$dbuser = "root";
$dbpass = "";
$dbname = "GFG";

// Create database connection
mysqli_connect($host, $dbuser, $dbpass, $dbname);

// Check connection
if(mysqli_connect_error())
{
 echo "Connection establishing failed!";
}
else
{
 echo "Connection established successfully.";
}
?>
```

**3。MySQL _ select _ db():**
这个 MySQL 函数是用来改变默认数据库进行连接的。

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```sql
<?php
// Database configuration
$host  = "localhost";
$dbuser = "root";
$dbpass = "";
$dbname = "GFG";
$dbtest = "GFG_TEST";

// Create database connection
$conn = mysqli_connect($host, $dbuser, $dbpass, $dbname);

//write some code for database "GFG"

// Change database to "GFG_TEST"
 mysqli_select_db($conn,$dbtest);

// PHP code for database "GFG_TEST"...

mysqli_close($conn);
?>
```

**结果:**
这会将当前数据库更改为 *GFG_TEST*
**4。MySQL _ debug():**
每个 web 开发人员都需要参考日志文件来开始故障排除，以提高应用性能。上述 mySQLi 函数在代码中用于所有调试目的。

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```sql
<?php
//create a trace file in the localhost
mysqli_debug("d:t:o,/temp/client.trace");
?>
```