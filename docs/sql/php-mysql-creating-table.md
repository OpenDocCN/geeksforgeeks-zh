# PHP | MySQL(创建表)

> 原文:[https://www.geeksforgeeks.org/php-mysql-creating-table/](https://www.geeksforgeeks.org/php-mysql-creating-table/)

**什么是桌子？**
在关系数据库和平面文件数据库中，表是使用垂直列和水平行模型的一组数据元素，单元格是行和列相交的单位。表有指定数量的列，但可以有任意数量的行。

**使用 MySQL 和 PDO**
创建一个 MySQL 表在[这篇](https://www.geeksforgeeks.org/php-mysql-creating-database/)的文章中，我们已经从 PHP 中学习了在 MySQL 中创建数据库。创建表的步骤类似于创建数据库。不同的是，我们将连接到现有的数据库，并在该数据库中创建一个表，而不是创建一个新的数据库。为了连接到现有的数据库，我们可以在连接到 MySQL 时传递一个额外的变量“数据库名”。

CREATE TABLE 语句用于在 MySQL 中创建一个表。

在本文中，将创建一个名为“employees”的表，该表有四列:“id”、“firstname”、“lastname”和“email”。

**将使用的数据类型为:**

1.  **VARCHAR:** 保存可变长度的字符串，可以包含字母、数字和特殊字符。括号中指定了最大大小。
2.  **INT:**INTEGER 数据类型接受隐含小数位数为零的数值。它存储-2147483648 到 2147483647 之间的任何整数值。

**本文中与数据类型一起使用的属性是:**

1.  **不为空:**每行必须包含该列的值，不允许为空值。
2.  **主键:**用于唯一标识表中的行。具有主键设置的列通常是一个标识号。

创建三个不同版本的表如下所述:

*   **Creating table using MySQLi Object-oriented Procedure**
    **Syntax :**

    ```sql
    <?php
    $servername = "localhost";
    $username = "username";
    $password = "password";
    $dbname = "newDB";

    // checking connection
    $conn = new mysqli($servername, $username, $password, $dbname);
    // Check connection
    if ($conn->connect_error) {
        die("Connection failed: " . $conn->connect_error);
    }

    // sql code to create table
    $sql = "CREATE TABLE employees(
            id INT(2)  PRIMARY KEY, 
            firstname VARCHAR(30) NOT NULL,
            lastname VARCHAR(30) NOT NULL,
            email VARCHAR(50)
            )";

    if ($conn->query($sql) === TRUE) {
        echo "Table employees created successfully";
    } else {
        echo "Error creating table: " . $conn->error;
    }

    $conn->close();
    ?>

    ```

    **输出:**
    ![](img/1770ca93a6bcc984765a785d634e7524.png)

*   **Creating table using MySQLi Procedural procedure**
    **Syntax :**

    ```sql
    <?php
    $servername = "localhost";
    $username = "username";
    $password = "password";
    $dbname = "newDB";

    // Checking connection
    $conn = mysqli_connect($servername, $username, $password, $dbname);
    // Check connection
    if (!$conn) {
        die("Connection failed: " . mysqli_connect_error());
    }

    // sql code to create table
    $sql = "CREATE TABLE employees (
            id INT(2)  PRIMARY KEY, 
            firstname VARCHAR(30) NOT NULL,
            lastname VARCHAR(30) NOT NULL,
            email VARCHAR(50)
            )";

    if (mysqli_query($conn, $sql)) {
        echo "Table employees created successfully";
    } else {
        echo "Error creating table: " . mysqli_error($conn);
    }
    mysqli_close($conn);
    ?>

    ```

    **输出:**
    ![](img/1770ca93a6bcc984765a785d634e7524.png)

*   **Creating table using PDO procedure**
    **Syntax :**

    ```sql
    <?php
    $servername = "localhost";
    $username = "username";
    $password = "password";
    $dbname = "newDB";

    try {
        $conn = new PDO("mysql:host=$servername;dbname=$dbname", 
                                                    $username, $password);

        // setting the PDO error mode to exception
        $conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);

        // sql code to create table
        $sql = "CREATE TABLE employees (
                id INT(6) UNSIGNED AUTO_INCREMENT PRIMARY KEY, 
                firstname VARCHAR(30) NOT NULL,
                lastname VARCHAR(30) NOT NULL,
                email VARCHAR(50)
                )";

        // using exec() because no results are returned
        $conn->exec($sql);
        echo "Table employees created successfully";
        }
    catch(PDOException $e)
        {
        echo $sql . "
    " . $e->getMessage();
        }

    $conn = null;
    ?>

    ```

    **输出:**
    ![](img/1770ca93a6bcc984765a785d634e7524.png)