# SQL Server 中的 GETUTCDATE()函数

> 原文:[https://www . geeksforgeeks . org/getutctdate-function-in-SQL-server/](https://www.geeksforgeeks.org/getutcdate-function-in-sql-server/)

获取 TCDATE() :

SQL Server 中的此函数用于以“YYYY-MM-DD hh:mm:ss.mmm”模式返回当前数据库系统的世界协调时日期和时间。

**功能:**

*   This function is used to find the UTC date and time of the current database system.
*   This function belongs to the date function.
*   The function does not accept any parameters.
*   The function returns the output in the format' yyyy-mm-ddhh: mm: ss.mmm'

**语法:**

```sql
GETUTCDATE()
```

**参数:**

此方法不接受任何参数。

**返回:**

它以' YYYY-MM-DD hh:mm:ss.mmm '格式返回当前数据库系统的世界协调时日期和时间。

**示例-1 :**

使用 GETUTCDATE()函数并获取输出。

```sql
SELECT GETUTCDATE();
```

**输出:**

```sql
2021-01-03 15:34:14.403
```

这里，每次编译代码时，输出都会有所不同，因为此方法返回当前的世界协调时日期和时间。

**示例-2 :**

在下面的示例中使用 GETUTCDATE()作为默认值并获取输出。

```sql
CREATE TABLE get_utc_date
(
   id_num        INT IDENTITY,
   message        VARCHAR(150) NOT NULL,
   generated_at DATETIME NOT NULL
   DEFAULT GETUTCDATE(),
   PRIMARY KEY(id_num)
);
INSERT INTO get_utc_date(message)
VALUES('Its the first message.');

INSERT INTO get_utc_date(message)
VALUES('get_utc_date');

SELECT
     id_num,
     message,
     generated_at
FROM
     get_utc_date;
```

**输出:**

```sql
  |id_num |  message              |   generated_at
-------------------------------------------------------------  
1 | 1     | Its the first message.| 03.01.2021 17:32:16
-------------------------------------------------------------
2 | 2     | get_utc_date          | 03.01.2021 17:32:16
```

在这里，首先需要创建一个表，然后向其中插入值，然后使用 GETUTCDATE()函数作为默认值生成所需的输出。

**注意:**对于运行上述代码使用 SQL server 编译器，也可以使用在线编译器。

**示例-3 :**

使用 CONVERT()函数，以便仅将 GETUTCDATE()函数的输出转换为当前日期。

```sql
SELECT CONVERT(DATE, GETUTCDATE());
```

**输出:**

```sql
2021-01-07
```

这里，每次编译代码时，输出可能会有所不同，因为它返回的是当前日期。

**示例-4 :**

使用 CONVERT()函数，以便仅将 GETUTCDATE()函数的输出转换为当前时间。

```sql
SELECT CONVERT(TIME, GETUTCDATE());
```

**输出:**

```sql
06:40:14.4700000
```

这里，每次编译代码时，输出可能会有所不同，因为它返回当前时间。

**应用:**

该函数用于返回数据库系统的当前世界协调时日期和时间。