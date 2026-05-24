# MySQL 中的 YEARWEEK()函数

> 原文:[https://www.geeksforgeeks.org/yearweek-function-in-mysql/](https://www.geeksforgeeks.org/yearweek-function-in-mysql/)

**YEARWEEK** ()函数在 MySQL 中用于查找给定日期的年和周。如果日期为空，YEARWEEK()函数将返回空值。否则，它将返回介于 1000 到 9999 之间的年值和介于 0 到 53 之间的周值。

**语法:**

```sql

YEARWEEK(date, mode)

```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Date:** We want to extract the date or date time of year and week from it.
*   **Mode:** Specify which day the week starts. The following table describes how mode parameters work.

T34】1T36】周一 T38】0-0 年

| model | The first day of the week | range | The first week is the first week … |
| --- | --- | --- | --- |
| Zero | Sunday | 0-53 | There is a Sunday this year. |
| three | Monday | 1-53 | There are four days or more this year. |
| four | Sunday | 0-53 | There are four days or more this year. |
| five |
| seven | Monday | 1-53 | Use a Monday this year. |

**返回:**返回年和周的值。

**示例-1 :** 使用 2020 年 9 月 28 日的 Year()函数查找当前年份和星期。

```sql
SELECT YEARWEEK(NOW()) AS Current_YearWeek;

```

**输出:**

```sql
+------------------+
| Current_YearWeek |
+------------------+
|           202039 |
+------------------+
1 row in set (0.00 sec)

```

所以，今年是 2020 年，周数是 39。

**示例-2 :** 使用 YEARWEEK()函数从给定的日期时间中查找年和周。

```sql
SELECT YEARWEEK('2018-04-22 08:09:22') AS Year_Week ;

```

**输出:**

```sql
+-----------+
| Year_Week |
+-----------+
|    201816 |
+-----------+

```

所以，在这个例子中，年份是 2018 年，周数是 16。

**示例-3 :** 当日期为空时，使用 YEARWEEK()函数从给定的日期时间中查找年和周。

```sql
SELECT YEARWEEK(NULL) AS Year_Week ;

```

**输出:**

```sql
+-----------+
| Year_Week |
+-----------+
|    NULL   |
+-----------+

```

**示例-4 :** 在本例中，我们将查找一年中每周注册课程的学生人数。演示创建一个名为。

**路线:**T0】

现在在产品表中插入一些数据:

```sql
INSERT INTO 
    Course(Course_Name, Student_id, Student_name, Enroll_Date)
VALUES
    ( 'CS101', 161011, 'Amit Singh', '2019-11-26' ),
    ( 'CS101', 161029, 'Arun Kumar', '2019-11-30' ),
    ( 'CS101', 161031, 'Sanya Jain', '2019-12-08' ),
    ( 'CS101', 161058, 'Riya Shah', '2019-12-15' ),
    ( 'CS101', 162051, 'Amit Sharma', '2019-12-18' ),
        ( 'CS101', 161951, 'Sayan Singh', '2019-12-26' ),
        ( 'CS101', 167051, 'Rishi Jana', '2020-01-02' ),
    ( 'CS101', 168001, 'Aniket Dravid', '2020-01-10' ),
    ( 'CS101', 168051, 'Rita Singh', '2020-01-13' ),
    ( 'CS101', 166051, 'Kalyan Ghandi', '2020-01-26' ) ;

```

所以，我们的桌子看起来像:

```sql
mysql> select * from Course;
+-------------+------------+---------------+-------------+
| Course_name | Student_id | Student_name  | Enroll_Date |
+-------------+------------+---------------+-------------+
| CS101       |     161011 | Amit Singh    | 2019-11-26  |
| CS101       |     161029 | Arun Kumar    | 2019-11-30  |
| CS101       |     161031 | Sanya Jain    | 2019-12-08  |
| CS101       |     161058 | Riya Shah     | 2019-12-15  |
| CS101       |     161951 | Sayan Singh   | 2019-12-26  |
| CS101       |     162051 | Amit Sharma   | 2019-12-18  |
| CS101       |     166051 | Kalyan Ghandi | 2020-01-26  |
| CS101       |     167051 | Rishi Jana    | 2020-01-02  |
| CS101       |     168001 | Aniket Dravid | 2020-01-10  |
| CS101       |     168051 | Rita Singh    | 2020-01-13  |
+-------------+------------+---------------+-------------+
10 rows in set (0.00 sec)

```

现在，我们将找到每周和每年注册该课程的学生人数。

```sql
SELECT 
    YEARWEEK(Enroll_Date) YearandWeek, 
    COUNT(Student_id) Student_Enrolled
FROM 
    Course
GROUP BY YEARWEEK(Enroll_Date)
ORDER BY YEARWEEK(Enroll_Date);

```

**输出:**

```sql
+-------------+------------------+
| YearandWeek | Student_Enrolled |
+-------------+------------------+
|      201947 |                2 |
|      201949 |                1 |
|      201950 |                2 |
|      201951 |                1 |
|      201952 |                1 |
|      202001 |                1 |
|      202002 |                1 |
|      202004 |                1 |
+-------------+------------------+
8 rows in set (0.00 sec).

```