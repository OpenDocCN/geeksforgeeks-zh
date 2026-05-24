# PHP | MySQL WHERE 子句

> 原文:[https://www.geeksforgeeks.org/php-mysql-clause/](https://www.geeksforgeeks.org/php-mysql-clause/)

**WHERE** 子句用于仅过滤那些由用户给出的特定条件满足的记录。换句话说，SQL WHERE 子句用于限制受 SELECT、UPDATE 或 DELETE 查询影响的行数。

**语法:**
where 子句的基本语法是–
**SELECT column 1，Column2，…。
从表 _ 名称
条件**

#### WHERE 条款的实施:

让我们考虑下表“数据”，其中有三列“名字”、“姓氏”和“年龄”。

![](img/98fcb773143afa30c197fe8f96d76360.png)

要选择“名字”为“ram”的所有行，我们将使用以下代码:

**使用程序方法的条款:**

```sql
<?php
$link = mysqli_connect("localhost", "root", "", "Mydb");

if($link === false){
    die("ERROR: Could not connect. "
                . mysqli_connect_error());
}

$sql = "SELECT * FROM Data WHERE Firstname='ram'";
if($res = mysqli_query($link, $sql)){
    if(mysqli_num_rows($res) > 0){
        echo "<table>";
            echo "<tr>";
                echo "<th>Firstname</th>";
                echo "<th>Lastname</th>";
                echo "<th>age</th>";
            echo "</tr>";
        while($row = mysqli_fetch_array($res)){
            echo "<tr>";
                echo "<td>" . $row['Firstname'] . "</td>";
                echo "<td>" . $row['Lastname'] . "</td>";
                echo "<td>" . $row['Age'] . "</td>";
            echo "</tr>";
        }
        echo "</table>";
        mysqli_free_result($res);
    } else{
        echo "No Matching records are found.";
    }
} else{
    echo "ERROR: Could not able to execute $sql. " 
                                . mysqli_error($link);
}

mysqli_close($link);
?>
```

**输出:**
![](img/30a3df2a4cac0792727c5f3b4445294e.png)

**代码说明:**

1.  “res”变量存储函数 *mysql_query()* 返回的数据。
2.  每次调用 MySQL _ fetch _ array()时，它都会返回 *res()* 集合中的下一行。
3.  while 循环用于循环遍历表“数据”的所有行。

**使用面向对象方法的 Where 子句:**

```sql
<?php
$mysqli = new mysqli("localhost", "root", "", "Mydb");

if($mysqli === false){
    die("ERROR: Could not connect. " 
                . $mysqli->connect_error);
}

$sql = "SELECT * FROM Data WHERE Firstname='ram'";
if($res = $mysqli->query($sql)){
    if($res->num_rows > 0){
        echo "<table>";
            echo "<tr>";
                echo "<th>Firstname</th>";
                echo "<th>Lastname</th>";
                echo "<th>Age</th>";
            echo "</tr>";
        while($row = $res->fetch_array()){
            echo "<tr>";
                echo "<td>" . $row['Firstname'] . "</td>";
                echo "<td>" . $row['Lastname'] . "</td>";
                echo "<td>" . $row['Age'] . "</td>";
            echo "</tr>";
        }
        echo "</table>";
        $res->free();
    } else{
        echo "No matching records are found.";
    }
} else{
    echo "ERROR: Could not able to execute $sql. " 
                                    . $mysqli->error;
}

$mysqli->close();
?>
```

**输出:**
![](img/30a3df2a4cac0792727c5f3b4445294e.png)

**使用 PDO 方法的 Where 子句:**

```sql
<?php
try{
    $pdo = new PDO("mysql:host=localhost;
                    dbname=Mydb", "root", "");
    $pdo->setAttribute(PDO::ATTR_ERRMODE, 
                        PDO::ERRMODE_EXCEPTION);
} catch(PDOException $e){
    die("ERROR: Could not connect. " 
                    . $e->getMessage());
}

try{
    $sql = "SELECT * FROM Data WHERE Firstname='ram'"; 
    $res = $pdo->query($sql);
    if($res->rowCount() > 0){
        echo "<table>";
            echo "<tr>";
                echo "<th>Firstname</th>";
                echo "<th>Lastname</th>";
                echo "<th>Age</th>";
            echo "</tr>";
        while($row = $res->fetch()){
            echo "<tr>";
                echo "<td>" . $row['Firstname'] . "</td>";
                echo "<td>" . $row['Lastname'] . "</td>";
                echo "<td>" . $row['Age'] . "</td>";
            echo "</tr>";
        }
        echo "</table>";
        unset($res);
    } else{
        echo "No records matching are found.";
    }
} catch(PDOException $e){
    die("ERROR: Could not able to execute $sql. " 
                                   . $e->getMessage());
}

unset($pdo);
?>
```

**输出:**
![](img/30a3df2a4cac0792727c5f3b4445294e.png)