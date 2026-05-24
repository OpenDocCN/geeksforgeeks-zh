# 在 SQL server 中将值或表达式从一种数据类型转换为另一种数据类型

> 原文:[https://www . geesforgeks . org/将一个数据类型的值或表达式转换为另一个 SQL server/](https://www.geeksforgeeks.org/casting-value-or-an-expression-from-one-data-type-to-another-in-sql-server/)

SQL Server 使用 CAST()函数将值或表达式从一种数据类型转换为另一种数据类型。

**语法:**

```sql
CAST ( value AS targettype [ ( length ) ] )

```

**使用的参数:**

*   **值–**
    值可以是将被转换的任何类型的任何值。

*   **target type–**
    target type 是将值转换为的目标数据类型。例如 INT、BIT、SQL_VARIANT 等。*   **length –**
    length is an optional parameter that specifies the length of the targettype, default length is 30.

    为了更好地理解，让我们运行如下查询。

    ```sql
    SELECT 3 + '3' AS Result;
    ```

    **输出:**

    | 结果 |
    | --- |
    | six |

    其结果是 6 作为一个数字。在上面的语句中，SQL Server 将字符串“3”隐式转换为数字 3。

    **注意–**
    当 SQL Server 中使用两个不同数据类型的值时，如果进一步处理，会先将较低的数据类型转换为较高的数据类型。这就是所谓的隐式转换。

    另一方面，SQL server 可以使用显式转换，其中 CAST()函数显式用于将一种类型的值转换为另一种类型，如下所示。

    ```sql
    SELECT 3 + CAST('3' AS INT) AS Result;
    ```

    **输出:**

    | 结果 |
    | --- |
    | six |

    为了在不同的场景中强制转换数据类型的值，SQL Server 将根据以下规则返回截断值或舍入值，如下所示。

    | 来自数据类型 | 至数据类型 | 行为 |
    | --- | --- | --- |
    | 数字的 | 数字的 | 轮次 |
    | 数字的 | （同 Internationalorganizations）国际组织 | 缩短 |
    | 漂浮物 | （同 Internationalorganizations）国际组织 | 轮次 |
    | 漂浮物 | 数字的 | 轮次 |
    | 漂浮物 | 日期时间 | 轮次 |
    | 日期时间 | （同 Internationalorganizations）国际组织 | 轮次 |

    **示例–**

    *   **Example-1 :**
        Below example uses the CAST() function to convert the decimal type value to an integer type value.

        ```sql
        SELECT CAST(5.95 AS INT) AS Result;
        ```

        **输出:**

        | 结果 |
        | --- |
        | five |

    *   **Example-2 :**
        Below example uses the CAST() function to convert the decimal type value to another decimal type value number with the zero scale.

        ```sql
        SELECT CAST(5.95 AS DEC(3, 0)) Result;
        ```

        **输出:**

        | 结果 |
        | --- |
        | six |

    *   **Example-3 :**
        Using the CAST() function to convert a string to a datetime value example.
        The below example uses the CAST() function to convert the string to a datetime.

        ```sql
        SELECT CAST('2020-09-14' AS DATETIME) 
        AS Result;
        ```

        **输出:**

        | 结果 |
        | --- |
        | 2020-09-14 00:00:00.000 |