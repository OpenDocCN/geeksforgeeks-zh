# PL/SQL 中的有用日期和时间函数

> 原文:[https://www . geesforgeks . org/有用的日期和时间函数 in-pl-sql/](https://www.geeksforgeeks.org/useful-date-and-time-functions-in-pl-sql/)

日期和时间函数格式在不同的数据库中是不同的。我们将讨论 Oracle 数据库中最常用的函数。

函数 **SYSDATE** 返回 7 字节数据，包括:

*   百年
*   年
*   月
*   一天
*   小时
*   分钟
*   第二

**1。提取():**
甲骨文帮助您使用提取()函数从日期中提取年、月和日。

*   **Example-1:** Extracting Year:

    ```sql
    SELECT SYSDATE AS CURRENT_DATE_TIME, EXTRACT(Year FROM SYSDATE) AS ONLY_CURRENT_YEAR
    FROM Dual
    ```

    **输出:**

    | 当前日期时间 | 仅 _ 当前 _ 年 |
    | 05.2019 年 2 月 07 日 29 时 24 分 | Two thousand and nineteen |

    **说明:**
    仅用于从系统日期/当前日期或特定指定日期检索**年份**。

*   **Example-2:** Extracting Month:

    ```sql
    SELECT SYSDATE AS CURRENT_DATE_TIME, EXTRACT(Month FROM SYSDATE) AS ONLY_CURRENT_MONTH
    FROM Dual
    ```

    **输出:**

    | 当前日期时间 | 仅当前月份 |
    | 05.2019 年 2 月 07 日 29 时 24 分 | 二月（February 的缩写） |

    **说明:**
    仅用于从系统日期/当前日期或特定指定日期中检索**月**。

*   **Example-3:** Extracting Day:

    ```sql
    SELECT SYSDATE AS CURRENT_DATE_TIME, EXTRACT(Day FROM SYSDATE) AS ONLY_CURRENT_DAY
    FROM Dual
    ```

    **输出:**

    | 当前日期时间 | 仅 _ 当前 _ 日 |
    | 05.2019 年 2 月 07 日 29 时 24 分 | five |

    **说明:**
    仅从系统日期/当前日期或特定指定日期检索**日**有用。

**2。ADD _ MONTES(date，n):**
在 PL/SQL 中使用这种方法，您可以在一个日期中添加和减去月数(n)。这里**‘n’**既可以是负数，也可以是正数。

*   **Example-4:**

    ```sql
    SELECT ADD_MONTHS(SYSDATE, -1)  AS PREV_MONTH, SYSDATE AS CURRENT_DATE, 
                                     ADD_MONTHS(SYSDATE, 1) as NEXT_MONTH
    FROM Dual
    ```

    **输出:**

    | PREV_MONTH | 当前日期 | 下个月 |
    | 02.2019 年 1 月 09 日 15 时 46 分 | 02.2019 年 2 月 09 日 15 时 46 分 | 02.2019 年 3 月 09 日 15 时 46 分 |

    **解释:**
    ADD_MONTHS 函数有两个参数一个是日期，其中可以是任何指定/特定日期或系统日期作为当前日期，第二个是' n '，它是一个整数值，可以是正的或负的，以获得即将到来的日期或之前的日期。

**3。LAST_DAY(日期):**
在 PL/SQL 中使用这个方法可以得到指定日期所在月份的最后一天。

*   **Example-5:**

    ```sql
    SELECT SYSDATE AS CURRENT_DATE, LAST_DAY(SYSDATE) AS LAST_DAY_OF_MONTH, 
                                    LAST_DAY(SYSDATE)+1 AS FIRST_DAY_OF_NEXT_MONTH
    FROM Dual
    ```

    **输出:**

    | 当前日期 | 每月最后一天 | 下个月第一天 |
    | 02.2019 年 2 月 09:32:00 | 28.2019 年 2 月 09:32:00 | 01.2019 年 3 月 09:32:00 |

    **解释:**
    在上面的例子中，我们使用 SYSDATE 函数获取当前日期，并且使用 LAST_DAY 函数检索当月的最后一天，该函数也有助于检索下个月的第一天。

*   **Example-6:** Number of Days left in the month

    ```sql
    SELECT SYSDATE AS CURRENT_DATE, LAST_DAY(SYSDATE) - SYSDATE AS DAYS_LEFT_IN_MONTH
    FROM Dual
    ```

    **输出:**

    | 当前日期 | 月 _ 日 _ 左 _ 中 _ 月 |
    | 02.2019 年 2 月 09:32:00 | Twenty-six |

**4。月 _ 月(日期 1，日期 2):**
在 PL/SQL 中使用此方法，您可以计算日期 1 和日期 2 这两个输入日期之间的月数。如果日期 1 晚于日期 2，则结果为正，如果日期 1 早于日期 2，则结果为负。

**注意:**
如果计算的是分数月份，则 MONTHS_BETWEEN 函数根据 31 天的月份计算分数。

*   **Example-7:**

    ```sql
    SELECT MONTHS_BETWEEN (TO_DATE ('01-07-2003', 'dd-mm-yyyy'), 
                           TO_DATE ('14-03-2003', 'dd-mm-yyyy')) AS NUMBER_OF_MONTHS
    FROM Dual
    ```

    **输出:**

    | 月数 |
    | Three point five eight |

    **解释:**
    这里日期 1 和日期 2 不在一个月的同一天，这就是为什么我们用分数来取值，同时日期 1 晚于日期 2，所以结果值是整数。
    Eneterd 日期应该是特定的日期格式，这也是在 MONTHS_BETWEEN 函数内比较时使用 TO_DATE 函数的原因。

    让我们选择员工为公司工作的月数。

*   **Example-8:**

    ```sql
    SELECT MONTHS_BETWEEN (SYSDATE, DATE_OF_HIRE) AS NUMBER_OF_MONTHS
    FROM Employees
    ```

    **输入:**

    | 系统日期 | 雇佣日期 |
    | 02-02-2019 | 31-10-2017 |
    | 02-02-2019 | 03-12-2017 |
    | 02-02-2019 | 24-09-2018 |
    | 02-02-2019 | 22-12-2016 |
    | 02-02-2019 | 18-06-2018 |

    **输出:**

    | 月数 |
    | Fifteen point zero six four |
    | Thirteen point nine six seven |
    | Four point two nine |
    | Twenty-five point three five four |
    | Seven point four eight three |

**5。NEXT_DAY(日期，星期几):**
它将返回晚于输入日期的第一个工作日的即将到来的日期。它有两个参数第一个日期，可以输入系统日期或指定日期；一周的第二天，应该是字符形式。

*   **Example-9:**

    ```sql
    SELECT NEXT_DAY(SYSDATE, 'SUNDAY') AS NEXT_SUNDAY
    FROM Dual
    ```

    **输出:**

    | 下周日 |
    | 2019 年 2 月 17 日 |

    **说明:**
    提供下一个即将到来的日期对应当天会有帮助，返回类型始终是 date，与数据类型 DATE 无关。第二个参数必须是一周中的某一天的全名或缩写。