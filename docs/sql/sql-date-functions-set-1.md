# SQL |日期函数(集-1)

> 原文:[https://www.geeksforgeeks.org/sql-date-functions-set-1/](https://www.geeksforgeeks.org/sql-date-functions-set-1/)

在 SQL 中，日期对于新手来说很复杂，因为在使用数据库时，表中日期的格式必须与输入日期相匹配才能插入。在各种场景中，使用日期时间(时间也与日期相关)代替日期。

一些重要的日期功能已经在之前的[帖子](https://www.geeksforgeeks.org/sql-date-functions/)中讨论过了。这篇文章的基本思想是了解所有日期函数的工作原理或语法:

下面是 SQL 中使用的日期函数:

1.  **ADDDATE():** 它在添加了某个时间/日期间隔后返回一个日期。

    ```sql
    Syntax: SELECT ADDTIME("2018-07-16 02:52:47", "2");
    ```

    **输出:**2018-07-16 02:52:49

2.  **ADDTIME():**添加一定时间间隔后返回时间/日期时间。

    ```sql
    Syntax: SELECT ADDTIME("2017-06-15 09:34:21", "2");
    ```

    **输出:**2017-06-15 09:34:23

3.  **cordate():**返回当前日期。

    ```sql
    Syntax: SELECT CURDATE();
    ```

    **输出:**2018-07-16

4.  **CURRENT _ DATE():**返回当前日期。

    ```sql
    Syntax: SELECT CURRENT_DATE();
    ```

    **输出:**2018-07-16

5.  **CURRENT _ TIME():**返回当前时间。

    ```sql
    Syntax: SELECT CURRENT_TIME();
    ```

    **输出:**02:53:15

6.  **CURRENT _ TIMESTAMP():**返回当前日期和时间。

    ```sql
    Syntax: SELECT CURRENT_TIMESTAMP();
    ```

    **输出:**2018-07-16 02:53:21

7.  **CURTIME():**返回当前时间。

    ```sql
    Syntax: SELECT CURTIME();
    ```

    **输出:**02:53:28

8.  **DATE():**它从日期或日期时间表达式中提取日期值。

    ```sql
    Syntax: SELECT DATE("2017-06-15");
    ```

    **输出:**2017-06-15

9.  **DATEDIFF():**返回两个日期值的天差。

    ```sql
    Syntax: SELECT DATEDIFF("2017-06-25", "2017-06-15");
    ```

    **输出:**10

10.  **DATE _ ADD():**添加一定的时间/日期间隔后返回日期。

    ```sql
    Syntax: SELECT DATE_ADD("2018-07-16", INTERVAL 10 DAY);
    ```

    **输出:**2018-07-16

11.  **DATE _ FORMAT():**按照格式掩码指定的格式设置日期。

    ```sql
    Syntax: SELECT DATE_FORMAT("2018-06-15", "%Y");
    ```

    **输出:**2018

12.  **DATE _ SUB():**减去一定的时间/日期间隔后返回日期。

    ```sql
    Syntax: SELECT DATE_SUB("2017-06-15", INTERVAL 10 DAY);
    ```

    **输出:**2018-07-16

13.  **DAY():**返回日期值的日部分。

    ```sql
    Syntax: SELECT DAY("2018-07-16");
    ```

    **输出:**16

14.  **day name():**返回某个日期的工作日名称。

    ```sql
    Syntax: SELECT DAYNAME('2008-05-15');
    ```

    **输出:**星期四

15.  **DAYOFMONTH():** 返回日期值的日部分。

    ```sql
    Syntax: SELECT DAYOFMONTH('2018-07-16');
    ```

    **输出:**16

16.  **day week():**返回某个日期值的工作日索引。

    ```sql
    Syntax: SELECT WEEKDAY("2018-07-16");
    ```

    **输出:**0

17.  **DAYOFYEAR():**返回一年中的某一天作为日期值。

    ```sql
    Syntax: SELECT DAYOFYEAR("2018-07-16");
    ```

    **输出:**197

18.  **EXTRACT():**它从一个日期中提取零件。

    ```sql
    Syntax: SELECT EXTRACT(MONTH FROM "2018-07-16");
    ```

    **输出:**7

19.  **FROM _ DAYS():**它从一天的数字表示中返回一个日期值。

    ```sql
    Syntax: SELECT FROM_DAYS(685467);
    ```

    **输出:**1876-09-29

20.  **HOUR():**返回日期值的小时部分。

    ```sql
    Syntax: SELECT HOUR("2018-07-16 09:34:00");
    ```

    **输出:**9

21.  **LAST _ DAY():**返回给定日期当月的最后一天。

    ```sql
    Syntax: SELECT LAST_DAY('2018-07-16');
    ```

    **输出:**2018-07-31

22.  **LOCALTIME():**返回当前日期和时间。

    ```sql
    Syntax: SELECT LOCALTIME();
    ```

    **输出:**2018-07-16 02:56:42

23.  **LOCALTIMESTAMP():**返回当前日期和时间。

    ```sql
    Syntax: SELECT LOCALTIMESTAMP();
    ```

    **输出:**2018-07-16 02:56:48

24.  **MAKEDATE():**返回某年某月某日的日期值。

    ```sql
    Syntax: SELECT MAKEDATE(2009, 138);
    ```

    **输出:**2009-05-18

25.  **MAKETIME():**返回一定小时、分钟、秒组合的时间。

    ```sql
    Syntax: SELECT MAKETIME(11, 35, 4);
    ```

    **输出:**11:35:04