# MySQL 中 WEEKOFYEAR()函数

> 原文:[https://www.geeksforgeeks.org/weekofyear-function-in-mysql/](https://www.geeksforgeeks.org/weekofyear-function-in-mysql/)

MySQL 中的 WEEKOFYEAR()函数用于查找给定日期的周数。如果日期为空，WEEKOFYEAR 函数将返回空值。否则，它将返回 1 到 53 之间的周值。

**语法:**

```sql
WEEKOFYEAR( date)
```

**参数:**
此方法只接受一个参数。

*   **日期–**我们要从中提取周数的日期或日期时间。

**返回:**
返回周数。

**例-1:**
2020 年 9 月 29 日使用 WEEKOFYEAR()函数查找当前周数。

```sql
SELECT WEEKOFYEAR(NOW()) AS Current_Week;

```

**输出:**

| 当前 _ 周 |
| --- |
| Forty |

所以，当前周数是 40。

**示例-2 :**
使用 WEEKOFYEAR()函数从给定的日期时间中查找星期。

```sql
SELECT WEEKOFYEAR('2018-04-22 08:09:22') 
AS Week_Number ;

```

**输出:**

| 周数 |
| --- |
| Sixteen |

在这个例子中，周数是 16。

**示例-3 :**
使用 WEEKOFYEAR()函数查找给定日期的周。

```sql
SELECT WEEKOFYEAR('2019-07-25 ') 
AS Week_Number ;

```

**输出:**

| 周数 |
| --- |
| Thirty |

**示例-4 :**
当日期为空时，使用 WEEKOFYEAR()函数从给定的日期时间中查找周数。

```sql
SELECT WEEKOFYEAR(NULL) 
AS Week_Number;

```

**输出:**

| 周数 |
| --- |
| 空 |

**示例-4 :**
在本例中，我们将查找一年中每周注册一门课程的学生人数。演示创建一个名为。**当然。**

```sql
CREATE TABLE  Course
(
    Course_name  VARCHAR(100) NOT NULL,
    Student_id INT NOT NULL,  
    Student_name VARCHAR(100) NOT NULL,
    Enroll_Date Date NOT NULL,
    PRIMARY KEY(Student_id)
);

```

现在向课程表中插入一些数据。

```sql
INSERT INTO
Course(Course_Name, Student_id, Student_name, Enroll_Date)
VALUES
    ( 'CS101', 161011, 'Amit Singh', '2019-10-06' ),
    ( 'CS101', 161029, 'Arun Kumar', '2019-10-23' ),
    ( 'CS101', 161031, 'Sanya Jain', '2019-11-08' ),
    ( 'CS101', 161058, 'Riya Shah', '2019-11-20' ),
    ( 'CS101', 162051, 'Amit Sharma', '2019-11-30' ),
    ( 'CS101', 161951, 'Sayan Singh', '2019-12-07' ),
    ( 'CS101', 167051, 'Rishi Jana', '2019-12-15' ),
    ( 'CS101', 168001, 'Aniket Dravid', '2019-12-25' ),
    ( 'CS101', 168051, 'Rita Singh', '2019-12-28' ),
    ( 'CS101', 166051, 'Kalyan Ghandi', '2019-12-29' ) ;

```

所以，我们的桌子看起来像。

| 课程名称 | 学生 id | 学生名称 | 注册 _ 日期 |
| --- | --- | --- | --- |
| CS101 | One hundred and sixty-one thousand and eleven | 我是辛格 | 2019-10-06 |
| CS101 | One hundred and sixty-one thousand and twenty-nine | 阿伦·库马尔 | 2019-10-23 |
| CS101 | One hundred and sixty-one thousand and thirty-one | 三亚耆那教 | 2019-11-08 |
| CS101 | One hundred and sixty-one thousand and fifty-eight | 理雅沙 | 2019-11-20 |
| CS101 | One hundred and sixty-two thousand and fifty-one | 和 Sharma 一样 | 2019-11-30 |
| CS101 | One hundred and sixty-one thousand nine hundred and fifty-one | 萨扬·辛格 | 2019-12-07 |
| CS101 | One hundred and sixty-seven thousand and fifty-one | 笑一笑 Jana | 2019-12-15 |
| CS101 | One hundred and sixty-eight thousand and one | 我是丹尼 | 2019-12-25 |
| CS101 | One hundred and sixty-eight thousand and fifty-one | 丽塔·辛格 | 2019-12-28 |
| CS101 | One hundred and sixty-six thousand and fifty-one | Kalyan Ghandi | 2019-12-39 |

现在，我们要找出每周注册这门课程的学生人数。

```sql
SELECT
WEEKOFYEAR(Enroll_Date) Week_Number,
COUNT(Student_id) Student_Enrolled
FROM
    Course
    GROUP BY WEEKOFYEAR(Enroll_Date)
    ORDER BY WEEKOFYEAR(Enroll_Date);

```

**输出:**

| 周数 | 学生 _ 已注册 |
| --- | --- |
| Forty | one |
| Forty-three | one |
| Forty-five | one |
| Forty-seven | one |
| Forty-eight | one |
| forty-nine | one |
| Fifty | one |
| fifty-two | three |