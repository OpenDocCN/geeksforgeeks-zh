# SQL |案例语句

> 原文:[https://www.geeksforgeeks.org/sql-case-statement/](https://www.geeksforgeeks.org/sql-case-statement/)

控制语句是大多数语言的核心，因为它们控制其他语句集的执行。这些也可以在 SQL 中找到，应该通过仔细选择符合我们要求的元组来利用它们进行查询过滤和查询优化。在这篇文章中，我们探讨了 SQL 中的 Case-Switch 语句。
CASE 语句是 SQL 处理 if/then 逻辑的方式。
**语法:**
**可以有两种有效的方法来处理大小写转换语句。**

1.  第一种方法采用一个名为 case_value 的变量，并将其与某个 statement_list 进行匹配。

    ```sql
    CASE case_value
        WHEN when_value THEN statement_list
        [WHEN when_value THEN statement_list] ...
        [ELSE statement_list]
    END CASE

    ```

2.  第二种方法考虑 search_condition 而不是变量 equality，并相应地执行语句 _list。

    ```sql
    CASE
        WHEN search_condition THEN statement_list
        [WHEN search_condition THEN statement_list] ...
        [ELSE statement_list]
    END CASE

    ```

    **示例:**

    假设我们有关系，教员。

    **教员表:**

    | 光斑 ID | 名字 | 部门 | 性别 |
    | 001 | 阿卡巴 | 特许测量员 | M |
    | 002 | 在海滩上 | 欧盟委员会（European Commission） | M |
    | 003 | 约翰 | 高速钢（high-speed steel 的缩写） | M |
    | 004 | 雪莱 | 特许测量员 | F |
    | 005 | 阿南尼亚 | 特许测量员 | F |
    | 006 | 希雅·凯特·伊索贝尔·富勒 | 高速钢（high-speed steel 的缩写） | F |

    假设我们希望修改此表，这样如果部门名称为“CS”，则修改为“计算机科学”，如果部门名称为“EC”，则修改为“电子与通信”，如果部门名称为“HSS”，则修改为“人文与社会科学”。这可以通过使用 case 语句来实现。

    **示例查询:**
    考虑一个变量，在 SQL 代码中输入的 department_name。

    ```sql
    CASE department_name
     WHEN 'CS'
      THEN UPDATE Faculty SET
      department='Computer Science';
     WHEN 'EC'
      THEN UPDATE Faculty SET
      department='Electronics and Communication';
     ELSE UPDATE Faculty SET
     department='Humanities and Social Sciences';
    END CASE

    ```

    输出:

    ```sql
    The department name corresponding to the given input gets renamed.

    ```

    考虑另一个查询，该查询选择对应于教员表的所有字段。由于在性别字段中写入的值是单字符值(M/F)，我们希望以更易读的格式呈现它们。

    ```sql
    SELECT FacultyID, Name, Department,
    CASE Gender
     WHEN'M' THEN 'Male'
     WHEN'F' THEN 'Female'
    END
    FROM Faculty

    ```

    **输出:**

    | 光斑 ID | 名字 | 部门 | 性别 |
    | 001 | 阿卡巴 | 特许测量员 | 男性的 |
    | 002 | 在海滩上 | 欧盟委员会（European Commission） | 男性的 |
    | 003 | 约翰 | 高速钢（high-speed steel 的缩写） | 男性的 |
    | 004 | 雪莱 | 特许测量员 | 女性的 |
    | 005 | 阿南尼亚 | 特许测量员 | 女性的 |
    | 006 | 希雅·凯特·伊索贝尔·富勒 | 高速钢（high-speed steel 的缩写） | 女性的 |

    再考虑一下 SQL 定制排序中大小写切换的另一个应用。

    ```sql
    CREATE PROCEDURE GetFaculty(@ColToSort varchar(150)) AS
    SELECT FacultyID, Name, Gender, Department
    FROM Customers
    ORDER BY
      CASE WHEN @ColToSort='Department' THEN Department
           WHEN @ColToSort='Name' THEN Name
           WHEN @ColToSort='Gender' THEN Gender
           ElSE FacultyID
      END 

    ```

    输出:

    ```sql
    The output gets sorted according to the provided field.

    ```

    上面的过程(函数)以 varchar 数据类型的变量作为参数，并在此基础上对教工表中的元组进行排序。

    本文由 **Anannya Uberoi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。