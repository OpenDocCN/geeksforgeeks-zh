# SQL Server 中的 CURRENT_TIMESTAMP()函数

> 原文:[https://www . geesforgeks . org/current _ timestamp-function-in-SQL-server/](https://www.geeksforgeeks.org/current_timestamp-function-in-sql-server/)

**CURRENT_TIMESTAMP()函数:**
SQLServer 中的这个[函数用于返回当前日期和时间。输出的格式如下。](https://www.geeksforgeeks.org/categories-of-sql-functions/)

```sql
'YYYY-MM-DD hh:mm:ss.mmm'
```

**特征:**

*   该函数用于查找当前日期和时间。
*   该功能属于*日期功能。*
*   这个函数不接受任何参数。
*   在某些代码中，该函数也可以用作默认值。

**语法:**

```sql
CURRENT_TIMESTAMP
```

**参数:**
此方法不接受任何参数。

**返回:**
返回当前日期和时间，返回的输出格式为‘YYYY-MM-DD hh:MM:ss . mmm’。

**示例-1 :**
使用 CURRENT_TIMESTAMP 函数，获取当前日期和时间。

```sql
SELECT CURRENT_TIMESTAMP 
AS current_date_and_time;
```

**输出:**

```sql
current_date_and_time
--------------------------
2020-12-31 12:32:24.100
```

因此，每次运行这段代码时，输出可能会有所不同，因为这个函数会返回当前的日期和时间。

**示例-2 :**
在下面的示例中使用 CURRENT_TIMESTAMP 作为默认值并获取输出。

```sql
CREATE TABLE current_time_stamp
(
    id_num INT IDENTITY, 
    message VARCHAR(150) NOT NULL, 
    generated_at DATETIME NOT NULL
    DEFAULT CURRENT_TIMESTAMP, 
    PRIMARY KEY(id_num)
);

```

**将数据插入表格–**

```sql
INSERT INTO current_time_stamp(message)
VALUES('Its the first message.');

INSERT INTO current_time_stamp(message)
VALUES('current_time_stamp');

```

**从表中读取数据–**

```sql
SELECT 
    id_num, 
    message, 
    generated_at
FROM 
    current_time_stamp;
```

**输出:**

<figure class="table">T22【2020】31 . 12 . 2020 15:57:01

| index number | id_num | news | Generate _ at |
| one | one | The first message. |
| Two | Two | 当前时间戳 | 31 . 12 . 2020 15:57:01 |

</figure>

在这里，首先需要创建一个表，然后向其中插入值，然后使用 CURRENT _ TIMPLATE 函数作为默认值生成所需的输出。

**注意–**
对于运行上述代码使用 SQL server 编译器，也可以使用在线编译器。

**应用:**
此功能用于查找当前日期和时间。