# SQL 中的日期操作函数

> 原文:[https://www . geesforgeks . org/date-operating-functions-in-SQL/](https://www.geeksforgeeks.org/date-manipulating-functions-in-sql/)

为了从表中操作和获取日期值，oracle 内置了日期函数。这里，我们将介绍 SQL 中的
日期操作函数。

1.  **ADD_MONTHS :**
    It will add the total number of months specified in n to the date parameter and Returns date.

    **语法**:

    ```sql
    ADD_MONTHS(d, n)
    ```

    **示例–**

    ```sql
    Select ADD_MONTHS(SYSDATE, 4) 
    "Add months" from dual;

    ```

    **输出:**

    ```sql
    Add Months
    01-NOV-04

    ```

2.  **LAST_DAY :**
    In the LAST_DAY function, It will return the last date of the month, and for the specified month like if the system date is 1 Nov then it will return 30 Nov.

    **语法:**

    ```sql
    LAST_DAY(date)
    ```

    **示例-**

    ```sql
    Select SYSDATE, LAST_DAY(SYSDATE) 
    "Last Day" from dual;

    ```

    **输出:**

    ```sql
    SYSDATE                Last Day
    01-NOV-04             30-NOV-04

    ```

3.  **MONTHS_BETWEEN :**
    Returns number of months between date1 and date2.

    **语法:**

    ```sql
    MONTHS_BETWEEN(date1, date2)
    ```

    **示例–**

    ```sql
    Select MONTHS_BETWEEN('02-FEB-00', '01-JAN-00') 
    "Months" from dual;

    ```

    **输出:**

    ```sql
    Months
      1

    ```

4.  **NEXT_DAY :**
    It will return the date of the first weekday that comes after the date specified in *date parameter*. char specified should be someday of the week.

    **语法:**

    ```sql
    NEXT_DAY(date, char)
    ```

    **示例–**

    ```sql
    SELECT NEXT_DAY('06-JUL-02', 'saturday') 
    "Next day" from dual;

    ```

    这里返回下周六的日期。
    **输出:**

    ```sql
    Next day
    13-JUL-02

    ```

5.  **NEW_TIME :**
    Returns the date after converting it from time *zone 1* to a date in time *zone 2*.

    **语法:**

    ```sql
    NEW_TIME(date, zone1, zone2)
    ```

    <figure class="table">

    | **值** | **描述** | **值** | **描述** |
    | --- | --- | --- | --- |
    | 大西洋时间 | 大西洋时间 | 大西洋夏令时间 | 大西洋夏令时 |
    | 牛生长激素 | 白令标准时间 | BDT | 白令夏令时 |
    | 中央标准时间 | 中部标准时间 | 中央日光时间 | 中央采光时间 |
    | GreenwichMeanTime 格林尼治标准时间 | 格林威治标准时间 | 期刊 | 纽芬兰标准时间 |
    | HDT | 阿拉斯加-夏威夷夏令时 | 高速列车 | 阿拉斯加-夏威夷标准时间 |
    | 山区夏令时 | 山区日光时间 | 山地时间 | 山区标准时间 |
    | 悄悄话 | 太平洋标准时 | 太平洋夏季时间 | 太平洋夏令时 |

    </figure>

    **示例–**

    ```sql
    Select NEW_TIME(To_date('2004/07/01 01:45', 'yyyy/mm/dd HH24:MI'), 
    'AST', 'MST') "MST" from dual;

    ```

    **输出:**

    ```sql
    MST
    30-JUN-04

    ```

    这将大西洋标准时间转换为山区标准时间。