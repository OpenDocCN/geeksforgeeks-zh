# PHP | MySQL 数据库介绍

> 原文:[https://www . geesforgeks . org/PHP-MySQL-database-introduction/](https://www.geeksforgeeks.org/php-mysql-database-introduction/)

**什么是 MySQL？**
[MySQL](https://www.geeksforgeeks.org/structured-query-language/) 是一个开源的关系数据库管理系统(RDBMS)。它是与 PHP 一起使用的最流行的数据库系统。MySQL 是由甲骨文公司开发、分发和支持的。

*   MySQL 数据库中的数据存储在由列和行组成的表中。
*   MySQL 是一个运行在服务器上的数据库系统。
*   MySQL 是小型和大型应用程序的理想选择。
*   MySQL 是非常快速、可靠、易用的数据库系统。它使用标准的 SQL
*   MySQL 在许多平台上编译。

**下载 MySQL 数据库**
MySQL 可以从[这个](http://www.mysql.com/)链接免费下载。

**PHP 如何和 MySQL 数据库连接？**
PHP 5 及更高版本可以使用以下方式使用 MySQL 数据库:

1.  MySQLi 扩展。
2.  PDO。

**MySQL 和 PDO 的区别**

*   PDO 在 12 个不同的数据库系统上工作，而 MySQL 只在 MySQL 数据库上工作。
*   PDO 和 MySQL 都是面向对象的，但是 MySQL 也提供了一个过程 API。
*   如果在开发阶段的某个时候，用户或开发团队想要更改数据库，那么在 PDO 比在 MySQLi 更容易，因为 PDO 支持 12 个不同的数据库系统。他只需要更改连接字符串和一些查询。使用 MySQLi，他将需要重写包括查询在内的整个代码。

**使用 MySQl 和 PHP 有三种方式**

1.  MySQLi(面向对象)
2.  MySQLi(程序性)
3.  PDO〔t0〕

**使用 PHP 连接 MySQl 数据库**
我们有 3 种方法可以从 PHP 连接到 MySQL，如上所列，如下所述:

*   **Using MySQLi object-oriented procedure**: We can use the MySQLi object-oriented procedure to establish a connection to MySQL database from a PHP script. 

    **语法**:

```sql
<?php
$servername = "localhost";
$username = "username";
$password = "password";

// Creating connection
$conn = new mysqli($servername, $username, $password);

// Checking connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
} 
echo "Connected successfully";
?>
```

**输出:**

![](img/a46501b4ae25f55a9937f32b7f79b1b2.png)

**解释**:我们可以创建一个**MySQL**类的实例，提供建立连接所需的所有必要细节，如主机、用户名、密码等。如果实例创建成功，则连接成功，否则在建立连接时会出现一些错误。

*   **Using MySQLi procedural procedure** : There is also a procedural approach of MySQLi to establish a connection to MySQL database from a PHP script as described below. 

    **语法:**

```sql
<?php
$servername = "localhost";
$username = "username";
$password = "password";

// Creating connection
$conn = mysqli_connect($servername, $username, $password);

// Checking connection
if (!$conn) {
    die("Connection failed: " . mysqli_connect_error());
}
echo "Connected successfully";
?>
```

**输出:**

![](img/a46501b4ae25f55a9937f32b7f79b1b2.png)

**解释**:在 MySQL 的过程化方法中，我们可以使用 PHP 中可用的 mysqli _ connect()函数来建立连接，而不是创建一个实例。该函数将信息作为参数，如主机、用户名、密码、数据库名等。该函数在成功连接时返回 MySQL 链接标识符，在建立连接失败时返回 FALSE。

*   **Using PDO procedure**: PDO stands for PHP Data Objects. That is, in this method we connect to the database using data objects in PHP as described below: 

    **语法:**

```sql
<?php
$servername = "localhost";
$username = "username";
$password = "password";

try {
    $conn = new PDO("mysql:host=$servername;dbname=myDB", $username, $password);
    // setting the PDO error mode to exception
    $conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
    echo "Connected successfully"; 
    }
catch(PDOException $e)
    {
    echo "Connection failed: " . $e->getMessage();
    }
?>
```

**输出:**

![](img/a46501b4ae25f55a9937f32b7f79b1b2.png)

**解释:**PDO 的异常类用于处理我们的数据库查询中可能出现的任何问题。如果在 try{ }块中引发异常，脚本将停止执行，并直接流向第一个 catch(){ }块。

**关闭连接**

当我们从一个 PHP 脚本建立到 MySQL 数据库的连接时，我们也应该在工作完成后断开或关闭连接。在这里，我们已经用上面描述的三种方法描述了关闭与 MySQL 数据库的连接的语法。我们假设对连接的引用存储在$conn 变量中。

*   **使用 MySQLi 面向对象程序**
    **语法**

```sql
$conn->close();
```

*   **使用 MySQLi 程序程序**
    **语法**

```sql
mysqli_close($conn);
```

*   **使用 PDO 程序**
    **语法**

```sql
$conn = null;
```