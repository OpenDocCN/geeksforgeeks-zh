# MySQL 中的 FROM_UNIXTIME()函数

> 原文:[https://www . geesforgeks . org/from _ unixtime-function-in-MySQL/](https://www.geeksforgeeks.org/from_unixtime-function-in-mysql/)

**FROM _ UNIXTIME():**
MySQL 中的这个函数有助于返回 Unix 时间戳的日期/日期时间表示。返回值的格式将是“YYYY-MM-DD HH:MM:SS”或“YYYYMMDDHHMMSS”，具体取决于函数的上下文。

**语法:**

```sql
FROM_UNIXTIME(unix_timestamp, format)
```

**参数:**
函数可以接受如下两个参数。

*   **unix_timestamp–**
    它是一个内部时间戳值，它的值可以由 UNIX _ TIMESTAMP()函数产生。
*   **格式–**
    结果值的格式

**结果:**
该函数将返回一个 Unix 时间戳的日期/日期时间表示。而返回值的格式会是‘YYYY-MM-DD HH:MM:SS’或‘yyyymmdhhmmss’，具体取决于函数的上下文。

**示例-1:**
FROM _ UNIXTIME()函数在一个参数下的工作。

```sql
SELECT FROM_UNIXTIME(599462400) 
AS Unix;
```

**输出:**

| 

Unix 操作系统

 |
| 1988-12-29 22:20:00 |

**示例-2 :**
分数秒 FROM_UNIXTIME()函数的工作原理。

```sql
SELECT FROM_UNIXTIME(599462445.99999) 
AS Unix;
```

**输出:**

| 

Unix 操作系统

 |
| 1988-12-29 22:20:45.99999 |

**示例-3 :**
两个参数都通过时 FROM_UNIXTIME()函数的工作。

*   **When format is ‘%W, %D %M %Y’ –**

    ```sql
    SELECT FROM_UNIXTIME(799462445, '%W, %D %M %Y') 
    AS Unix;
    ```

    **输出:**

    | 

    Unix 操作系统

     |
    | 1995 年 5 月 2 日星期二 |

*   **When format is ‘%h:%i %p, %D %M %Y’ –**

    ```sql
    SELECT FROM_UNIXTIME(799462445, '%h:%i %p, %D %M %Y') 
    AS Unix;
    ```

    **输出:**

    | 

    Unix 操作系统

     |
    | 一九九五年五月二日下午六时五十四分 |

**示例-4 :**
在数值上下文中使用 FROM_UNIXTIME()函数。

```sql
SELECT  
FROM_UNIXTIME(846562400) As 'String_form',
FROM_UNIXTIME(846562400) + 1 As 'Numeric_form';
```

**输出:**

| 字符串形式 | 数字形式 |
| 1996-10-28 21:13:20 | 19961028211321 |