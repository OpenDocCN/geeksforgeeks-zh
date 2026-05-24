# 如何对 JDBC 的表格内容进行排序？

> 原文: [https://www.geeksforgeeks.org/how-to-sort-contents-of-a-table-in-jdbc/](https://www.geeksforgeeks.org/how-to-sort-contents-of-a-table-in-jdbc/)

对表的内容进行排序意味着以有组织的方式重新排列记录，以使数据更有用。您可以通过在表中选择一列来对表中的所有记录进行排序，根据该列对数据进行排序。简单地说，当你对数据排序时，你按照逻辑顺序排列数据。

*   文本和数字可以按任何顺序排序，即升序或降序。
*   可以同时对一列或多列进行排序。
*   在 SQL 中，`order by` 子句用于在 `JDBC` 中对表内容进行排序。
*   默认情况下，某些数据库按升序对查询结果排序。但我们也可以按降序排序。
*   我们可以同时对一列或多列使用 `ORDER BY` 子句。

## 后续步骤

1.  导入必要的库。
2.  注册驱动类。
3.  通过提供地址、用户名和密码连接到您的数据库。
4.  创建您的 `Statement`。
5.  编写您的查询。
6.  执行您的查询并将结果存储在 `ResultSet` 中。
7.  显示结果。

```
How ORDER BY works:

query ----->       select * from Table_Name ORDER BY Column1,Column 2;

user table ----->  --------------------------------------------------
                 || id || Name || Age ||
                 ||      1      ||      Prateek  ||     20       ||
                 ||      4      ||      Chhavi   ||     21       ||
                 ||      3      ||      Aman     ||     22       ||
                 ||      2      ||      Kartikay ||     22       ||
                 ||      5      ||      Prakhar  ||    20        ||
                 --------------------------------------------------

Example 1:         select * from user ORDER BY id;

Output:           --------------------------------------------------
                 || id || Name || Age ||
                 ||      1      ||      Prateek  ||     20       ||
                 ||      2      ||      Kartikay ||     22       ||
                 ||      3      ||      Aman     ||     22       ||
                 ||      4      ||      Chhavi   ||     21       ||
                 ||      5      ||      Prakhar  ||     20       ||
                 --------------------------------------------------

Example 2:         select * from user ORDER BY name,age;

Output:           --------------------------------------------------
                 || id || Name || Age ||
                 ||      3      ||      Aman     ||     22       ||
                 ||      4      ||      Chhavi   ||     21       ||
                 ||      2      ||      Kartikay ||     22       ||     
                 ||      5      ||      Prakhar  ||     20       ||
                 ||      1      ||      Prateek  ||     20       ||
                 --------------------------------------------------
```

## 例 1

## 爪哇

```java
// Java program to sort contents of a table

import java.sql.*;

public class GFG {

// driver code
    public static void main(String[] args) throws Exception
    {

// Register Driver Class
        Class.forName("org.apache.derby.jdbc.ClientDriver");

// Connection to your database, pass all the
        // necessary parameters such as address , username &
        // password
        Connection con = DriverManager.getConnection();

// Create Statement
        Statement stmt = con.createStatement();

// Query to be executed
        String query = "Select * from users ORDER by id";

// Execute SQL query and store the result in any
        // variable
        ResultSet rs = stmt.executeQuery(query);

System.out.println("Id    Name    Age");
        while (rs.next()) {
            int id = rs.getInt("id");
            String name = rs.getString("name");
            int age = rs.getInt("age");
            System.out.println(id + "  " + name + "   "
                               + age);
        }

// close the connection
        con.close();
    }
}
```