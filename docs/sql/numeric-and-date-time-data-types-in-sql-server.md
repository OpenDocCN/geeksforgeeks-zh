# SQL Server 中的数字和日期时间数据类型

> 原文:[https://www . geesforgeks . org/numeric-date-time-data-type-in-SQL-server/](https://www.geeksforgeeks.org/numeric-and-date-time-data-types-in-sql-server/)

微软 SQL Server 支持多种数据类型。本文中包含了一些更重要的数据类型。在本文中，我们将介绍数值型 SQL server 数据类型和不同的日期时间数据类型。我们一个一个来讨论。

1.  **bit :**
    A bit is the smallest unit of a computer system. A bit can be either 0 or 1\. The bit datatype can take NULL values as well.

    **语法–**

    ```sql
    column_name bit; 
    ```

    一个位最多可以占用 8 个字节的存储空间，而 2 个位最多可以占用 16 个位，并且循环继续。

2.  **int :**
    A data type that can store integer values(positive and negative). The storage size is up to 8 bytes(-2⁶³ to 2⁶³-1). It is sub-categorized into tinyint, int, smallint, bigint. They can be used according to the number of bytes that can be stored.
    *   **(i). bigint –**
        A numeric integer datatype that has the maximum storage of 8 bytes.(-2⁶³ to 2⁶³-1). It can store positive and negative values as well. It can be used for storing huge numbers.

        **语法–**

        ```sql
        column_name bigint; 
        ```

    *   **(ii). int –**
        A numeric integer datatype having a storage size of 4 bytes.

        **语法–**

        ```sql
        column_name int; 
        ```

    *   **(iii). smallint –**
        A numeric integer type that stores 2 bytes of data.

        **语法–**

        ```sql
        column_name smallint; 
        ```

    *   **(四)。tinyint–**
        存储 1 个字节的数字数据类型。

    **语法–**

    ```sql
    column_name tinyint; 
    ```

    例如，班级表中的学生人数可以分配如下。

    ```sql
    rollnumber int;  
    ```

    SQL 服务器数值数据类型表:

    | 数字数据类型 | 整数大小(字节) |
    | --- | --- |
    | 少量 | 值(0、1 或空) |
    | 微缩 | one |
    | 斯莫列特 | 2  |
    | （同 Internationalorganizations）国际组织 | four |
    | 比吉斯本 | eight |
    | 十进制 | 5 至 17 岁 |
    | 数字(p，s) | 5 至 17 岁 |
    | 小额资金 | four |
    | 钱 | eight |
    | 浮动 | 4 或 8 |
    | 真实的 | four |

3.  **decimal :**
    A data type that can store decimal values. This datatype can be used for storing percentage values.

    **语法–**

    ```sql
    column_name decimal(precision, scale) 
    ```

    例如，

    ```sql
    percentage(4,3)  
    ```

    精度是用于描述从左到右存储的位数的术语，而刻度是用于存储小数点后位数的术语。

    以电子商务为例，产品交付日期和时间将存储在数据库中。对于这种情况，MS SQL SERVER 支持的数据类型很少:

4.  **date :**
    It stores the date in the format of yyyy-mm-dd.

    **语法–**

    ```sql
    date 
    ```

5.  **time :**
    It stores the time based on 24 hours clock.

    **语法–**

    ```sql
    time 
    ```

6.  **datetime2 :**
    It stores the date and time as well in the format of yyyy-mm-dd hh:mm: ss.

    **语法–**

    ```sql
    datetime2 
    ```

    有一些数据类型可以存储金钱、唯一标识符、XML 数据等等。但是，在 SQL Server 的未来版本中，由于某种原因，某些数据类型将被删除。确保使用 SQL Server 中可用的数据类型。SQL server 中不同类型的日期时间数据类型表，如下所示:

    | **数据类型** | **大小(字节)** |
    | 日期时间 | eight |
    | 日期时间 2 | 6 至 8 岁 |
    | smalldatetime | four |
    | 日期 | three |
    | 时间 | 3 至 5 |
    | datetimeoffset | 8 至 10 |
    | 时间戳 | 唯一的号码。 |