# SQL |空函数

> 原文:[https://www.geeksforgeeks.org/sql-null-functions/](https://www.geeksforgeeks.org/sql-null-functions/)

以下是在 SQL 中定义的空函数:

1.  **ISNULL(): **The ISNULL function have different uses in SQL Server and MySQL. In SQL Server, ISNULL() function is used to replace NULL values.
    **Syntax:**

    ```sql
    SELECT column(s), ISNULL(column_name, value_to_replace)
    FROM table_name;
    ```

    示例:
    考虑下面的员工表，

    ![](img/d0ddeedd67a8ece1912d5afcc64f431d.png)

    **查询:**查找所有员工的薪资之和，如果任意员工的薪资不可用(或为空值)，则使用薪资为 10000。

    ```sql
    SELECT SUM(ISNULL(Salary, 10000) AS Salary
    FROM Employee;
    ```

    输出:

    ![](img/d80dc7fc2ce8d6a565d93138951c2bc8.png)

    在 MySQL 中，ISNULL()函数用于测试表达式是否为空。如果表达式为空，则返回真，否则返回假。
    **语法:**

    ```sql
    SELECT column(s)
    FROM table_name
    WHERE ISNULL(column_name);
    ```

    示例:
    考虑下面的员工表，

    ![](img/2cad292ccc5f9ccfdc330aa5954d5e11.png)

    **查询:**取表中所有薪资可用的员工姓名(非空)。

    ```sql
    SELECT Name
    FROM Employee
    WHERE ISNULL(Salary);
    ```

    输出:

    ![](img/92290030965b9f3991f239387617f476.png)

2.  **IFNULL(): **This function is available in MySQL, and not in SQL Server or Oracle. This function take two arguments. If the first argument is not NULL, the function returns the first argument. Otherwise, the second argument is returned. This function is commonly used to replace NULL value with another value.
    **Syntax:**

    ```sql
    SELECT column(s), IFNULL(column_name, value_to_replace)
    FROM table_name;
    ```

    示例:
    考虑下面的员工表，

    ![](img/ed4be2106c11734f8aee2a6e906e1c4f.png)

    **查询:**查找所有员工的薪资之和，如果任意员工的薪资不可用(或为空值)，则使用薪资为 10000。

    ```sql
    SELECT SUM(IFNULL(Salary, 10000) AS Salary
    FROM Employee;
    ```

    输出:

    ![](img/f7364a79637525aeb47a7e1a121aea2b.png)

3.  **COALESCE(): **COALESCE function in SQL returns the first non-NULL expression among its arguments. If all the expressions evaluate to null, then the COALESCE function will return null.
    Syntax:

    ```sql
    SELECT column(s), CAOLESCE(expression_1,....,expression_n)
    FROM table_name;
    ```

    示例:
    考虑下面的 Contact_info 表，

    ![](img/b2bbd47aa5a9c92af64eee7002d58d46.png)

    **查询:**取每个员工的姓名、联系电话。

    ```sql
    SELECT Name, COALESCE(Phone1, Phone2) AS Contact
    FROM Contact_info;
    ```

    输出:

    ![](img/fec442c45f4905fef63488a82710199f.png)

4.  **NULLIF(): **The NULLIF function takes two argument. If the two arguments are equal, then NULL is returned. Otherwise the first argument is returned.
    Syntax:

    ```sql
    SELECT column(s), NULLIF(expression1, expression2)
    FROM table_name;
    ```

    示例:
    考虑下面的销售表，

    ![](img/045fa5d0f6ba5582b9ef29f476323ddf.png)

    ```sql
    SELECT Store, NULLIF(Actual, Goal)
    FROM Sales;
    ```

    输出:

    ![](img/81515c0c012d3e473da12e6b4da7db23.png)

本文由 **[Anuj Chauhan](https://www.facebook.com/anuj0503)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。