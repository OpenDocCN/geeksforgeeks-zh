# 在MySQL中插入DATETIME时的PHP DATE()格式

> Original: [https://www.geeksforgeeks.org/php-date-format-when-inserting-into-datetime-in-mysql/](https://www.geeksforgeeks.org/php-date-format-when-inserting-into-datetime-in-mysql/)

此问题描述了将日期插入MySQL数据库的日期格式。MySQL以`YYYY-MM-DD HH:MM:SS`格式检索和显示日期时间值。日期只能以此格式存储。但是，它可以与任何时间格式功能一起使用来更改和显示它。

当使用PHP在MySQL中编写查询时，将根据MySQL本身检查其适用性。因此，请使用MySQL提供的默认日期和时间格式`YYYY-MM-DD`。

## 日期格式说明

```php
DATE: YYYY-MM-DD
Example: 2005-12-26

DATETIME: YYYY-MM-DD HH:MI:SS
Example: 2005-12-26 23:50:30

TIMESTAMP: YYYY-MM-DD HH:MI:SS
Example: 2005-12-26 23:50:30

YEAR: YYYY or YY
```

## 创建数据库和表

**创建数据库的MySQL查询：**

```php
CREATE DATABASE Date_time_example;
```

**示例1：** 创建数据库和表的PHP程序

```php
<?php

$servername = "localhost";
$username = "root";
$password = "";
$dbname = "geeks";

// Create connection
$conn = mysqli_connect( $servername, $username, $password, $dbname );

// Check connection
if ( !$conn ) {
    die("Connection failed: " . mysqli_connect_error());
}

// SQL query to create table
$sql = "CREATE TABLE date_test (
    id INT AUTO_INCREMENT PRIMARY KEY,
    created_at DATETIME
)";

if (mysqli_query($conn, $sql)) {
    echo "Table date_test created successfully";
} else {
    echo "Error creating table: " . mysqli_error($conn);
}

// Close connection
mysqli_close($conn);
?>
```