# 如何在 SQL server 中把一个类型的值转换成另一个类型

> 原文:[https://www . geeksforgeeks . org/如何在 SQL server 中将一种类型的值转换为另一种类型/](https://www.geeksforgeeks.org/how-to-convert-a-value-of-one-type-to-another-type-in-sql-server/)

转换意味着改变某物的形式或价值。SQL server 中的 CONVERT()函数用于将一种类型的值转换为另一种类型。

**语法:**

```sql
SELECT CONVERT 
( target_type ( length ), expression ) 

```

**使用的参数:**

*   **target _ type–**
    是 to 表达式要转换成的目标数据类型，例如:INT、BIT、SQL_VARIANT 等。

*   **长度–**
    它提供了 target_type 的长度。长度不是强制性的。默认长度设置为 30。*   **expression –**
    expression is anything that will be converted.

    **示例-1 :**
    **将十进制数转换为整数:**
    在下面的示例中，convert()函数用于将十进制数 7.85 转换为整数。

    ```sql
    SELECT CONVERT(INT, 7.85) AS Result;

    ```

    **输出:**

    | 结果 |
    | --- |
    | seven |

    **示例-2 :**
    **将一个十进制数转换为另一个十进制数:**
    在下面的示例中，convert()函数用于将十进制数 8.99 转换为另一个零刻度的十进制数。

    ```sql
    SELECT CAST(8.99 AS DEC(2, 0)) 
    AS Result;
    ```

    **输出:**

    | 结果 |
    | --- |
    | nine |

    **示例-3 :**
    **要将字符串转换为日期时间值:**
    在下面的示例中，convert()函数用于将字符串' 2020-05-14 '转换为日期时间值。

    ```sql
    SELECT CONVERT(DATETIME, '2020-05-14') 
    AS Result;
    ```

    **输出:**

    | 结果 |
    | --- |
    | 2019-03-14 00:00:00.000 |

    **示例-4 :**
    **要将日期时间值转换为字符串:**
    在下面的示例中，convert()函数用于将当前日期和时间转换为具有确定样式的字符串。

    ```sql
    SELECT  CONVERT(VARCHAR, GETDATE(), 13) 
    AS Result;
    ```

    **输出:**

    | 结果 |
    | --- |
    | 2020 年 9 月 5 日 16:59:01:380 |