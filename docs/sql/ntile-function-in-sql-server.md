# SQL Server 中的 NTILE()函数

> 原文:[https://www.geeksforgeeks.org/ntile-function-in-sql-server/](https://www.geeksforgeeks.org/ntile-function-in-sql-server/)

**NTILE()** 函数在 [SQL Server](https://www.geeksforgeeks.org/sql-tutorial/) 中是一个窗口函数，它将有序分区的行分配到预定义数量的大致相等的组中。它为每个组分配一个范围为 1 的 number_expression。 **NTILE()** 函数为该行所属的组中的每一行分配一个 number_expression。

**语法:**

```sql
NTILE(number_expression) OVER (
   [PARTITION BY partition_expression ]
   ORDER BY sort_expression [ASC | DESC]
)

```

**详细语法参数:**

*   **number _ expression**
    number _ expression 是行被分成的整数。

*   **PARTITION BY 子句**
    PARTITION BY 是可选的，它将结果集的行划分为使用 NTILE()函数的分区。*   **ORDER BY clause**
    The ORDER BY clause defines the order of rows in each partition where the NTILE() is used.

    当行数不能被 number_expression 整除时，NTILE()函数会将两个大小的组的差除以 1。在 OVER()子句中的 ORDER BY 指定的顺序中，较大的组总是在较小的组之前。此外，当所有行都可以被 number_expression 整除时，该函数会在 number_expression 中平均分配行。

    **示例:**
    让我们创建一个名为 geeks_demo 的表:

    ```sql
    CREATE TABLE geeks_demo (
    ID INT NOT NULL );
    INSERT INTO geeks_demo(ID)
    VALUES(1), (2), (3), (4), (5), (6), (7), (8), (9), (10);

    ```

    现在，

    ```sql
    SELECT * 
    FROM geeks_demo;

    ```

    | 身份证明 |
    | --- |
    | one |
    | Two |
    | three |
    | four |
    | five |
    | six |
    | seven |
    | eight |
    | nine |
    | Ten |

    1.  **Use NTILE() function to divide above rows into 3 groups :**

        ```sql
        SELECT ID,
        NTILE (3) OVER (
        ORDER BY ID
        ) Group_number
        FROM geeks_demo; 
        ```

        **输出:**

        | 身份证明 | 组号 |
        | --- | --- |
        | one | one |
        | Two | one |
        | three | one |
        | four | one |
        | five | Two |
        | six | Two |
        | seven | Two |
        | eight | three |
        | nine | three |
        | Ten | three |

    2.  **Use the NTILE() function to distribute rows into 5 groups :**

        ```sql
        SELECT ID,
        NTILE (3) OVER (
        ORDER BY ID
        ) Group_number

        FROM geeks_demo; 
        ```

        **输出:**

        | 身份证明 | 组号 |
        | --- | --- |
        | one | one |
        | Two | one |
        | three | Two |
        | four | Two |
        | five | three |
        | six | three |
        | seven | four |
        | eight | four |
        | nine | five |
        | Ten | five |

    3.  **If someone try to run use the NTILE() function without number_expression :**

        ```sql
        SELECT ID,
        NTILE () OVER (
        ORDER BY ID
        ) Group_number

        FROM geeks_demo; 
        ```

        **输出:**
        会抛出以下错误:

        ```sql
        The function 'NTILE' takes exactly 1 argument(s). 

        ```