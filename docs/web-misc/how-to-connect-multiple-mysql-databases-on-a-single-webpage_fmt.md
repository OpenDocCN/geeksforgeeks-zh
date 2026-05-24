# 如何在一个网页上连接多个 MySQL 数据库？

> 原文: [https://www.geeksforgeeks.org/how-to-connect-multiple-mysql-databases-on-a-single-webpage/](https://www.geeksforgeeks.org/how-to-connect-multiple-mysql-databases-on-a-single-webpage/)

本文解释了如何将多个 MySQL 数据库连接到一个网页中。从多个数据库中访问数据非常有用。

有两种方法可以将多个 MySQL 数据库连接到一个网页中，它们是：

*   使用 MySQLi (MySQL 的改进版本)
*   使用 PDO (PHP 数据对象)

## 语法

### MySQLi 程序语法

> `$link = mysqli_connect("host_name", "user_name", "password", "database_name");`

### MySQLi 面向对象语法

> `$link = new mysqli("host_name", "user_name", "password", "database_name");`

### PDO (PHP 数据对象) 语法

> `$pdo = new PDO("mysql:host=host_name;dbname=database_name", "user_name", "password");`

## 程序

这个程序使用 MySQLi 在一个网页上连接多个数据库。

### PHP 代码

```php
<?php
// PHP program to connect multiple MySQL database
// into single webpage

// Connection of first database
// Database name => database1
// Default username of localhost => root
// Default password of localhost is '' (none)
$link1 = mysqli_connect("localhost", "root", "", "database1");

// Check for connection
if($link1 == true) {
    echo "database1 Connected Successfully";
}
else {
    die("ERROR: Could not connect " . mysqli_connect_error());
}

echo "<br>";

// Connection of second database
// Database name => database2
$link2 = mysqli_connect("localhost", "root", "", "database2");

// Check for connection
if($link2 == true) {
    echo "database2 Connected Successfully";
}
else {
    die("ERROR: Could not connect " . mysqli_connect_error());
}

echo "<br><br>Display the list of all Databases:<br>";

// Connection of databases
$link = mysqli_connect('localhost', 'root', '');

// Display the list of all database name
$res = mysqli_query($link, "SHOW DATABASES");

while( $row = mysqli_fetch_assoc($res) ) {
    echo $row['Database'] . "<br>";
}

?>
```

## 输出

![](img/73076df67c55a8a4fcc8e6f338b7d50a.png)