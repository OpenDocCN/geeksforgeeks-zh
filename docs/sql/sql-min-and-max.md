# SQL MIN()和 MAX()

> 原文:[https://www.geeksforgeeks.org/sql-min-and-max/](https://www.geeksforgeeks.org/sql-min-and-max/)

1.  **SQL MIN() Functions**
    The MIN() function provides the smallest value of the chosen column.

    **MIN()语法–**

    ```sql
    SELECT MIN(column_name)
    FROM table_name
    WHERE condition;

    ```

2.  **SQL MAX() Functions**
    The MAX() function provides the largest value of the chosen column.

    **MAX()语法–**

    ```sql
    SELECT MAX(column_name)
    FROM table_name
    WHERE condition;

    ```

让我们假设，我们有下表“GeeksTable”:

<center>

| 名字 | 城市 | 数字 | 薪水 | 告发 |
| --- | --- | --- | --- | --- |
| 字母表 | 德里 | One hundred and twenty-three | Four thousand | 8 月 4 日 |
| 极好的 | 孟买 | Three hundred and forty-five | Three thousand | 6 月 7 日至 |
| Mno | 德里 | Five hundred and sixty-seven | Two thousand nine hundred | 4 月 9 日至 |
| 字母表 | 无聊死了 | Four hundred and fifty-seven | Three thousand four hundred and fifty | 7 月 12 日至 |
| Xyz | 斋浦尔 | Eight hundred and seventy-six | Eight thousand seven hundred and fifty | 3 月 9 日至 |
| 荷航 | 德里 | Two hundred and thirty-four | Five thousand five hundred | 1 月 23 日至 |

</center>

1.  **MIN() Example :**
    The following SQL statement finds the lowest salary product :

    ```sql
    SELECT MIN(Salary) FROM GeeksTable;
    ```

    **输出–**

    ```sql
    2900
    ```

2.  **MAX() Example :**
    The following SQL statement finds the highest salary :

    ```sql
    SELECT MAX(Price) FROM GeeksTable; 
    ```

    **输出–**

    ```sql
    8750

    ```