# MySQL 中的 WEEK()函数

> 原文:[https://www.geeksforgeeks.org/week-function-in-mysql/](https://www.geeksforgeeks.org/week-function-in-mysql/)

**WEEK** ()函数在 MySQL 中用于查找给定日期的周数。如果日期为空，WEEK()函数将返回空值。否则，它将返回 0 到 53 之间的周值。

**语法:**

```sql
WEEK(date, mode)
```

**参数:**该方法接受语法中提到的双参数，描述如下–

*   **日期–**
    我们要从中提取星期的日期或日期时间。

*   **mode –**
    It specifies what day the week starts on. The following table describes how the mode argument works.

    **返回:**返回周数的值。

    | 方式 | 一周的第一天 | 范围 | 第一周是第一周… |
    | --- | --- | --- | --- |
    | Zero | 星期日 | 0-53 | 今年有一个星期天 |
    | one | 星期一 | 0-53 | 今年有 4 天或以上 |
    | Two | 星期日 | 1-53 | 今年有一个星期天 |
    | three | 星期一 | 1-53 | 今年有 4 天或以上 |
    | four | 星期日 | 0-53 | 今年有 4 天或以上 |
    | five | 星期一 | 0-53 | 今年的星期一 |
    | six | 星期日 | 1-53 | 今年有 4 天或以上 |
    | seven | 星期一 | 1-53 | 今年的星期一 |

    **例-1:**
    2020 年 10 月 15 日使用 week()函数查找当前周数。

    ```sql
    SELECT WEEK(NOW()) AS Current_Week;
    ```

    **输出:**

    | 当前 _ 周 |
    | --- |
    | Forty-one |

    所以，当前周数是 41。

    **示例-2 :**
    使用 Week()函数从给定的日期时间中查找星期。

    ```sql
    SELECT WEEK('2010-05-20 08:09:22') AS Week;
    ```

    **输出:**

    | 周 |
    | --- |
    | Twenty |

    在这个例子中，周数是 20。

    **示例-3 :**
    当日期为空时，使用 Week()函数从给定的日期时间中查找星期。

    ```sql
    SELECT WEEK(NULL) AS Week;
    ```

    **输出:**

    | 周 |
    | --- |
    | 空 |

    **示例-4 :**
    在本例中，我们将查找每周注册课程的学生人数。为了演示，创建一个名为“课程”的表。

    ```sql
    CREATE TABLE Course(
    Course_name  VARCHAR(100) NOT NULL,
    Student_id INT NOT NULL,  
    Student_name VARCHAR(100) NOT NULL,
    Enroll_Date Date NOT NULL,
    PRIMARY KEY(Student_id)
    );
    ```

    现在向课程表中插入一些数据–

    ```sql
    INSERT INTO  
    Course(Course_Name, Student_id, Student_name, Enroll_Date)
    VALUES
    ('CS101', 161011, 'Amit Singh', '2019-1-26'),
    ('CS101', 161029, 'Arun Kumar', '2019-5-30'),
    ('CS101', 161031, 'Sanya Jain', '2019-6-08'),
    ('CS101', 161058, 'Riya Shah', '2019-10-15'),
    ('CS101', 162051, 'Amit Sharma', '2019-10-18'),
    ('CS101', 161951, 'Sayan Singh', '2019-10-30'),
    ('CS101', 167051, 'Rishi Jana', '2019-11-02'),
    ('CS101', 168001, 'Aniket Dravid', '2019-11-10'),
    ('CS101', 168051, 'Rita Singh', '2019-11-13'),
    ('CS101', 166051, 'Kalyan Ghandi', '2019-12-26');
    ```

    **表–**课程

    | 课程名称 | 学生标识 | 学生姓名 | 注册日期 |
    | --- | --- | --- | --- |
    | CS101 | One hundred and sixty-one thousand and eleven | 我是辛格 | 2019-1-26 |
    | CS101 | One hundred and sixty-one thousand and twenty-nine | 阿伦·库马尔 | 2019-5-30 |
    | CS101 | One hundred and sixty-one thousand and thirty-one | 三亚耆那教 | 2019-6-08 |
    | CS101 | One hundred and sixty-one thousand and fifty-eight | 理雅沙 | 2019-10-15 |
    | CS101 | One hundred and sixty-two thousand and fifty-one | 和 Sharma 一样 | 2019-10-18 |
    | CS101 | One hundred and sixty-one thousand nine hundred and fifty-one | 萨扬·辛格 | 2019-10-30 |
    | CS101 | One hundred and sixty-seven thousand and fifty-one | 笑一笑 Jana | 2019-11-02 |
    | CS101 | One hundred and sixty-eight thousand and one | 我是丹尼 | 2019-11-10 |
    | CS101 | One hundred and sixty-eight thousand and fifty-one | 丽塔·辛格 | 2019-11-13 |
    | CS101 | One hundred and sixty-six thousand and fifty-one | Kalyan Ghandi | 2019-12-26 |

    现在，我们要找出每周注册这门课程的学生人数。

    ```sql
    SELECT WEEK(Enroll_Date) WeekNumber,  
    COUNT(Student_id) Student_Enrolled
    FROM Course
    GROUP BY WEEK(Enroll_Date)
    ORDER BY WEEK(Enroll_Date);
    ```

    **输出:**

    | 周数 | 学生 _ 已注册 |
    | --- | --- |
    | three | one |
    | Twenty-one | one |
    | Twenty-two | one |
    | Forty-one | Two |
    | Forty-three | Two |
    | Forty-five | Two |
    | Fifty-one | one |