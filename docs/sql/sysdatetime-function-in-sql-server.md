# SQL Server 中的 SYSDATETIME()函数

> 原文:[https://www . geesforgeks . org/sysdatetime-function-in-SQL-server/](https://www.geeksforgeeks.org/sysdatetime-function-in-sql-server/)

**sysdate():**

SQL Server 中的这个函数用于返回计算机当前运行 SQL Server 的日期和时间。

**功能:**

*   This function is used to find the date and time of the computer running SQL Server.
*   This function belongs to the date function.
*   The function does not accept any parameters.
*   The function returns the output in the format' yyyy-mm-ddhh: mm: ss.mmm'

**语法:**

```sql
SYSDATETIME()
```

**参数**:

此方法不接受任何参数。

**返回:**

它以“YYYY-MM-DD hh:mm:ss.mmm”格式返回计算机运行 SQL Server 的日期和时间。

**示例-1 :**

使用 SYSDATETIME()函数并获取输出。

```sql
SELECT SYSDATETIME();
```

**输出:**

```sql
2021-01-03 17:49:28.0575187
```

这里，每次编译代码时，输出都会有所不同，因为此方法返回当前日期和时间。

**示例-2 :**

在下面的示例中使用 SYSDATETIME()作为默认值并获取输出。

```sql
CREATE TABLE system_date_time
(
   id_num        INT IDENTITY,
   message        VARCHAR(150) NOT NULL,
   generated_at DATETIME NOT NULL
   DEFAULT SYSDATETIME(),
   PRIMARY KEY(id_num)
);
INSERT INTO system_date_time(message)
VALUES('Its the first message.');

INSERT INTO system_date_time(message)
VALUES('system_date_time');

SELECT
     id_num,
     message,
     generated_at
FROM
     system_date_time;
```

**输出:**

```sql
  |id_num |  message              |   generated_at 
-------------------------------------------------------------  
1 | 1     | Its the first message.| 03.01.2021 18:53:56
-------------------------------------------------------------
2 | 2     | system_date_time      | 03.01.2021 18:53:56
```

在这里，首先需要创建一个表，然后向其中插入值，然后使用 SYSDATETIME()函数作为默认值生成所需的输出。

**注意:**对于运行上述代码使用 SQL server 编译器，也可以使用在线编译器。

**示例-3 :**

使用 CONVERT()函数将 SYSDATETIME()函数的输出转换为当前日期。

```sql
SELECT CONVERT(DATE, SYSDATETIME());
```

**输出:**

```sql
2021-01-07
```

在这里，每次运行代码返回当前日期时，输出可能会有所不同。

**示例-4 :**

使用 CONVERT()函数将 SYSDATETIME()函数的输出转换为当前时间。

```sql
SELECT CONVERT(TIME, SYSDATETIME());
```

**输出:**

```sql
06:20:12.2400986
```

在这里，每次运行代码时，输出可能会有所不同，因为它会返回当前时间。

**应用:**

此函数用于返回运行 SQL server 的计算机的当前日期和时间。