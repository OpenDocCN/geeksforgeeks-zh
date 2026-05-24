# SQL 中一些有用的系统存储过程

> 原文:[https://www . geesforgeks . org/some-有用-系统-存储过程-in-sql/](https://www.geeksforgeeks.org/some-useful-system-stored-procedures-in-sql/)

SQL 中一些有用的系统[存储过程](https://www.geeksforgeeks.org/sql-procedures/)。

这些过程是内置过程，将有助于提取现有[用户定义存储过程](https://www.geeksforgeeks.org/what-is-stored-procedures-in-sql/)的定义和依赖关系。

*   **sp_help :**
    这将显示存储过程名称、模式名称、创建日期和时间，或者如果有任何参数，
    则显示参数名称、数据类型、长度、精度、规模、排序规则等。结果。
*   **sp_helptext :**
    这将显示结果存储过程的内容。

*   **sp_depends :**
    This will show where the procedure is dependent like name of tables, functions, etc.

    **示例–**
    假设我们有一个名为 geek_demo 的表:

    ```sql
    Select * from geek_demo ;
    ```

    **输出:**

    | 名字 | 薪水 | 城市 |
    | --- | --- | --- |
    | 鸭子！鸭子 | Twenty-four thousand five hundred | 德里 |
    | 巴比塔 | Twenty-three thousand six hundred | 无聊死了 |
    | 车坛 | Twenty-five thousand six hundred | 无聊死了 |
    | 迪帕克（男子名） | Twenty-four thousand three hundred | 德里 |
    | 伊莎！伊莎 | Twenty-five thousand nine hundred | 德里 |
    | 库希 | Twenty-four thousand six hundred | 无聊死了 |
    | 非常 | Twenty-five thousand five hundred | 无聊死了 |
    | 毛 | Twenty-three thousand nine hundred | 无聊死了 |

    让我们创建一个简单的存储过程，其中包含两个 Select 语句。

    ```sql
    CREATE PROCEDURE SelectGeek
    AS
    BEGIN
    SELECT TOP 3 [Name], [City], [Salary]
    FROM [geek_demo]
    ORDER BY [Salary] ASC
    SELECT TOP 3 [Name], [City], [Salary]
    FROM [geek_demo]
    ORDER BY [Salary] DESC
    END

    GO

    ```

    **调用存储过程:**

    ```sql
    EXEC SelectGeek ;
    ```

    **输出:**

    | 名字 | 城市 | 薪水 |
    | --- | --- | --- |
    | 巴比塔 | 无聊死了 | Twenty-three thousand six hundred |
    | 毛 | 无聊死了 | Twenty-three thousand nine hundred |
    | 迪帕克（男子名） | 德里 | Twenty-four thousand three hundred |

    | 名字 | 城市 | 薪水 |
    | --- | --- | --- |
    | 伊莎！伊莎 | 德里 | Twenty-five thousand nine hundred |
    | 车坛 | 无聊死了 | Twenty-five thousand six hundred |
    | 非常 | 无聊死了 | Twenty-five thousand five hundred |

    **sp _ help 存储过程示例:**

    ```sql
    SP_HELP SelectGeek ;
    ```

    **输出:**

    | 名字 | 物主 | 类型 | 创建时间 |
    | --- | --- | --- | --- |
    | 选择极客 | dbo | 存储过程 | 2020-09-29 14:59:26.943 |

    **sp _ help text 存储过程示例:**

    ```sql
    SP_HELPTEXT SelectGeek ;
    ```

    **输出:**

    ```sql
    Text

    CREATE PROCEDURE SelectGeek
    AS
    BEGIN
    SELECT TOP 3 [Name], [City], [Salary]
    FROM [geek_demo]
    ORDER BY [Salary] ASC
    SELECT TOP 3  [Name], [City], [Salary]
    FROM [geek_demo]
    ORDER BY [Salary] DESC
    END

    ```

    **sp _ dependent 存储过程示例:**

    ```sql
    SP_DEPENDS SelectGeek ;
    ```

    **输出:**

    | 名字 | 类型 | 更新 | 挑选 | 圆柱 |
    | --- | --- | --- | --- | --- |
    | dbo.geek_demo | 用户表 | 不 | 是 | 名字 |
    | dbo.geek_demo | 用户表 | 不 | 是 | 薪水 |
    | dbo.geek_demo | 用户表 | 不 | yaw-steering error 偏航导向误差 | 城市 |