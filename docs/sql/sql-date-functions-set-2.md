# SQL |日期函数(集合-2)

> 原文:[https://www.geeksforgeeks.org/sql-date-functions-set-2/](https://www.geeksforgeeks.org/sql-date-functions-set-2/)

在 SQL 中，日期对于新手来说很复杂，因为在使用数据库时，表中日期的格式必须与输入日期相匹配才能插入。在各种场景中，使用日期时间(时间也与日期相关)代替日期。

一些日期功能已经在 [Set-1](https://www.geeksforgeeks.org/sql-date-functions-set-1/) 中讨论过。在这篇文章中，已经讨论了剩余的日期函数。

下面是 SQL 中使用的剩余日期函数:

1.  **微秒():**它返回日期值的微秒部分。

    ```sql
    Syntax: SELECT MICROSECOND("2018-07-18 09:12:00.000345");
    ```

    **输出:** 345

2.  **MINUTE():** 返回日期值的分钟部分。

    ```sql
    Syntax: SELECT MINUTE("2018-07-18 09:12:00");
    ```

    **输出:** 12

3.  **MONTH():** 返回日期值的月份部分。

    ```sql
    Syntax: SELECT MONTH ('2018/07/18')AS MONTH;
    ```

    **输出:**7

4.  **MONTHNAME():**返回某个日期的完整月份名称。

    ```sql
    Syntax: SELECT MONTHNAME("2018/07/18");
    ```

    **输出:** JULY

5.  **NOW():** 返回当前日期和时间。

    ```sql
    Syntax: SELECT NOW();
    ```

    **输出:**2018-07-18 09:14:32

6.  **PERIOD _ ADD():**取一个期间，加上指定的月数。

    ```sql
    Syntax: SELECT PERIOD_ADD(201803, 6);
    ```

    **输出:**201809

7.  **PERIOD _ DIFF():**返回两个期间的月差。

    ```sql
    Syntax: SELECT PERIOD_DIFF(201810, 201802);
    ```

    **输出:** 8

8.  **QUARTER():** 返回日期值的四分之一部分。

    ```sql
    Syntax: SELECT QUARTER("2018/07/18");
    ```

    **输出:** 3

9.  **SECOND():** 返回日期值的第二部分。

    ```sql
    Syntax: SELECT SECOND("09:14:00:00032");
    ```

    **输出:**0

10.  **SEC _ TO _ TIME():**它将数字秒转换为时间值。

    ```sql
    Syntax: SELECT SEC_TO_TIME(1);
    ```

    **输出:**00:00:01

11.  **STR _ TO _ DATE():**取一个字符串，返回格式掩码指定的日期。

    ```sql
    Syntax:  SELECT STR_TO_DATE("JULY 18 2018", "%M %D %Y");
    ```

    **输出:**0018-07-18

12.  **SUBDATE():**返回一个日期，在该日期之后减去了某个时间/日期间隔。

    ```sql
    Syntax: SELECT SUBDATE("2017-06-15", INTERVAL 10 DAY);
    ```

    **输出:**2017-06-05

13.  **subiteme():**减去一定时间间隔后返回时间/日期时间值。

    ```sql
    Syntax: SELECT SUBDATE("2018/07/18", INTERVAL 10 DAY);
    ```

    **输出:**2018-07-18 09:15:17.542768

14.  **SYSDATE():**返回当前日期和时间。

    ```sql
    Syntax: SELECT SYSDATE();
    ```

    **输出:**2018-07-18 09:19:03

15.  **TIME():**它从一个时间/日期时间表达式中提取时间值。

    ```sql
    Syntax: SELECT TIME("09:16:10");
    ```

    **输出:**09:16:10

16.  **TIME _ FORMAT():**它按照格式掩码指定的格式设置时间。

    ```sql
    Syntax: SELECT TIME_FORMAT("09:16:10", "%H %I %S");
    ```

    **输出:**09 09 10

17.  **TIME _ TO _ SEC():**它将时间值转换为数字秒。

    ```sql
    Syntax: SELECT TIME_TO_SEC("09:16:10");
    ```

    **输出:**33370

18.  **TIMEDIFF():**返回两个时间/日期时间值的差值。

    ```sql
    Syntax: SELECT TIMEDIFF("09:16:10", "09:16:04");
    ```

    **输出:**00:00:06

19.  **TIMESTAMP():**它将表达式转换为日期时间值，如果指定，则为该值添加可选的时间间隔。

    ```sql
    Syntax: SELECT TIMESTAMP("2018-07-18", "09:16:10");
    ```

    **输出:**2018-07-18 09:16:10

20.  **TO _ DAYS():**它将日期转换为数字天。

    ```sql
    Syntax: SELECT TO_DAYS("2018-07-18");
    ```

    **输出:**737258

21.  **WEEK():**返回日期值的周部分。

    ```sql
    Syntax: SELECT WEEK("2018-07-18");
    ```

    **输出:**28

22.  **WEEKDAY():**返回日期值的 WEEKDAY 索引。

    ```sql
    Syntax: SELECT WEEKDAY("2018-07-18");
    ```

    **输出:**2

23.  **WEEKOFYEAR():**返回一年中某一周的日期值。

    ```sql
    Syntax: SELECT WEEKOFYEAR("2018-07-18");
    ```

    **输出:**29

24.  **YEAR():**返回日期值的年份部分。

    ```sql
    Syntax: SELECT YEAR("2018-07-18");
    ```

    **输出:**2018

25.  **year week():**返回日期值的年和周。

    ```sql
    Syntax:  SELECT YEARWEEK("2018-07-18");
    ```

    **输出:**201828