# SQL |高级功能

> 原文:[https://www.geeksforgeeks.org/sql-advanced-functions/](https://www.geeksforgeeks.org/sql-advanced-functions/)

以下是在 SQL 中定义的一些高级函数:

1.  **BIN():** It converts a decimal number to a binary number.
    **Syntax:**

    ```sql
    SELECT BIN(18);

    ```

    **输出:**
    ![](img/3bdf88afc6925afaedd45de707f88e1c.png)

2.  **BINARY():** It converts a value to a binary string
    **Syntax:**

    ```sql
    SELECT BINARY "GeeksforGeeks";
    ```

    **输出:**
    ![](img/b5020c935dff88e606efad78e61b9ef3.png)

3.  **聚结():**它返回列表中的第一个非空表达式。
    **语法:**

```sql
SELECT COALESCE(NULL,NULL,'GeeksforGeeks',NULL,'Geeks');

```

**输出:**
![](img/5833c7fe7fe7d309bd46489a1cddb5c1.png)

8.  **CONNECTION_ID():** It returns the unique connection ID for the current connection.
    **Syntax:**

    ```sql
    SELECT CONNECTION_ID();

    ```

    **输出:**
    ![](img/f5c77fbbd9893cdd06acd710b7f123a6.png)

9.  **CURRENT_USER():** It returns the user name and host name for the MySQL account used by the server to authenticate the current client.
    **Syntax:**

    ```sql
    SELECT CURRENT_USER();

    ```

    **输出:**
    ![](img/5913870dcabf8a235cda89190d025bbe.png)

10.  **DATABASE():** It returns the name of the default database.
    **Syntax:**

    ```sql
    SELECT DATABASE();

    ```

    **输出:**
    ![](img/4b96a8a9e8fb1a61885fddb2396d8433.png)

11.  **IF():** It returns one value if a condition is TRUE, or another value if a condition is FALSE.
    **Syntax:**

    ```sql
    SELECT IF(200<500, "YES", "NO");

    ```

    **输出:**
    ![](img/6eb98a06e52de8893e70a3b28c26e708.png)

12.  **LAST_INSERT_ID():** It returns the first AUTO_INCREMENT value that was set by the most recent INSERT or UPDATE statement.
    **Syntax:**

    ```sql
    SELECT LAST_INSERT_ID();

    ```

    **输出:**
    ![](img/3f18c94f9143d9499e7afc09c73bc2df.png)

14.  **Syntax:**

    ```sql
    SELECT NULLIF(25.11, 25);

    ```

    **输出:**
    ![](img/8ae000435143519e47dd78c8db51b216.png)

15.  **Syntax:**

    ```sql
    SELECT NULLIF(115, 115);

    ```

    **输出:**
    ![](img/ec6de4a72bea2a67fb361338af1674d8.png)

16.  **SESSION_USER():** It returns the user name and host name for the current MySQL user.
    **Syntax:**

    ```sql
    SELECT SESSION_USER();
    ```

    **输出:**
    ![](img/2d7ce55a433c9a2e9c97ff3f8fc14d0f.png)

17.  **SYSTEM_USER():** It returns the user name and host name for the current MySQL user.
    **Syntax:**

    ```sql
    SELECT SYSTEM_USER();

    ```

    **输出:**
    ![](img/648bb35456a20e1669cbcb2fb0bee6b4.png)

18.  **USER():** It returns the user name and host name for the current MySQL user.
    **Syntax:**

    ```sql
    SELECT USER();

    ```

    **输出:**
    ![](img/04fce8f8c68380abf776840ad286000f.png)

19.  **VERSION():** It returns the version of the MySQL database.
    **Syntax:**

    ```sql
    SELECT VERSION();

    ```

    **输出:**
    ![](img/150da8bad05e92b1b2888f949b03564a.png)