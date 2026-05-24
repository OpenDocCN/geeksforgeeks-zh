# Java 程序使用列的方法获取 JDBC 的列名

> 原文: [https://www.geeksforgeeks.org/java-program-to-use-methods-of-column-to-get-column-name-in-jdbc/](https://www.geeksforgeeks.org/java-program-to-use-methods-of-column-to-get-column-name-in-jdbc/)

Java 数据库连接或 JDBC 是一个 Java API（应用程序编程接口），用于通过 Java 应用程序执行数据库操作。它允许通过 Java 应用程序执行用于创建表和数据操作的 SQL 命令。Java 支持 `java.sql` 包，该包包含用于访问和处理存储在数据库中的数据的内置方法。`java.sql` 中的方法抛出 `SQLException`，因此代码块必须放在 `try` 块中，如果有任何异常，则让 `catch` 块处理异常。

## 程序

1.  `Class.forName()` 是一个用于加载驱动程序的静态类方法。
2.  接下来，使用 `DriverManager` 类的 `getConnection()` 方法建立与数据库的连接。`getConnection()` 接受 URL、用户名和密码来建立连接。`Statement` 中定义的方法用于与数据库交互。
    *   首先创建一个表，然后将记录插入到表中。
    *   SQL 命令通过 `addBatch()` 方法批量处理，并通过 `executeBatch()` 方法一次性执行。
    *   表中的记录被提取到 `ResultSet` 中。
    *   `ResultSet` 的 `getMetaData()` 方法用于获取提取到 `ResultSet` 中的记录的元数据。
    *   `ResultSetMetaData` 接口的 `getColumnCount()` 和 `getColumnName()` 方法用于获取表中的列数和每一列的名称。

## 例 1

```java
// Java Program to Use Methods of Column
// to get column name in JDBC

// Step 1: Importing DB files
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.ResultSetMetaData;
import java.sql.Statement;

// Class to get columns
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        try {

            // Step 2: Loading and registering drivers

            // Loading driver class
            // using forName() method
            Class.forName("oracle.jdbc.OracleDriver");

            // Step 3: Establishing the connection

            Connection con = DriverManager.getConnection(
                "jdbc:oracle:thin:@localhost:1521:xe",
                "username", "password");
            Statement s = con.createStatement();

            // Step 4: Create a statement
            String sql1
                = "CREATE TABLE ACADEMY(COURSE_ID VARCHAR2(20) PRIMARY KEY, COURSE_NAME VARCHAR2(20),MENTOR VARCHAR2(20),COURSE_FEE NUMBER)";

            // Step 5: Process the query
            // Inserting records in the table
            String sql2
                = "INSERT INTO ACADEMY VALUES('C101','MATH','ROBERT',5000)";
            String sql3
                = "INSERT INTO ACADEMY VALUES('C102','PHYSICS','JANE',8000)";
            String sql4
                = "INSERT INTO ACADEMY VALUES('C103','HISTORY','ADAM',6000)";
            String sql5
                = "INSERT INTO ACADEMY VALUES('C104','BIOLOGY','MARIE',5000)";
            String sql6
                = "INSERT INTO ACADEMY VALUES('C105','ENGLISH','ALBERT',3000)";
            s.addBatch(sql1);
            s.addBatch(sql2);
            s.addBatch(sql3);
            s.addBatch(sql4);
            s.addBatch(sql5);
            s.addBatch(sql6);

            // Step 6: Execute the statements
            // executing the sql commands
            s.executeBatch();

            // Obtaining the resultset
            ResultSet rs
                = s.executeQuery("SELECT * FROM ACADEMY");

            while (rs.next()) {

                System.out.println(
                    rs.getString(1) + "\t\t"
                    + rs.getString(2) + "\t\t"
                    + rs.getString(3) + "\t\t"
                    + rs.getString(4));
            }

            // Retrieving the ResultSetMetaData object
            ResultSetMetaData rsMetaData = rs.getMetaData();
            System.out.println(
                "List of column names in the current table: ");

            // Retrieving the list of column names
            int count = rsMetaData.getColumnCount();

            for (int i = 1; i <= count; i++) {
                System.out.print(rsMetaData.getColumnName(i)
                                 + "\t");
            }

            // Step 7: Close the connection
            con.commit();
            con.close();
        }

        // Catch block to handle exceptions
        catch (Exception e) {

            // Print the exception
            System.out.println(e);
        }
    }
}
```