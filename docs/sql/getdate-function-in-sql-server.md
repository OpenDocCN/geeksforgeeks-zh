# SQL Server 中的 GETDATE()函数

> 原文:[https://www . geesforgeks . org/get date-function-in-SQL-server/](https://www.geeksforgeeks.org/getdate-function-in-sql-server/)

**GETDATE()函数:**
SQL Server 中的这个函数用来以 **'YYYY-MM-DD hh:mm:ss.mmm'** 模式返回数据库系统当前的日期和时间。

**特征:**

*   该功能用于查找数据库系统的当前日期和时间。
*   该功能属于日期功能。
*   这个函数不接受任何参数。
*   该函数以“ **YYYY-MM-DD hh:mm:ss.mmm** 格式返回输出。

**语法:**

```sql
GETDATE()
```

**参数:**
此方法不接受任何参数。

**返回:**
以“ **YYYY-MM-DD hh:mm:ss.mmm** 格式返回数据库系统的当前日期和时间。

**示例-1 :**
使用 GETDATE()函数并获取输出。

```sql
SELECT GETDATE();
```

**输出:**

```sql
2021-01-03 14:42:58.970
```

这里，每次编译代码时，输出都会有所不同，因为此方法返回当前日期和时间。

**示例-2 :**
在下面的示例中使用 GETDATE()作为默认值并获取输出。

```sql
CREATE TABLE get_date
(
id_num INT IDENTITY, 
message VARCHAR(150) NOT NULL, 
generated_at DATETIME NOT NULL
DEFAULT GETDATE(), 
PRIMARY KEY(id_num)
);

```

**插入数据:**

```sql
INSERT INTO get_date(message)
VALUES('Its the first message.');

INSERT INTO get_date(message)
VALUES('get_date');

```

**读取数据:**

```sql
SELECT id_num, message, generated_at
FROM get_date;
```

**输出:**

<figure class="table">

| index number | id_num | news | Generate _ at |
| one | one | The first message. | 03 . 01 . 2021 15:49:48 |
| Two | Two | 获取日期 | 03 . 01 . 2021 15:49:48 |

</figure>

在这里，首先需要创建一个表，然后向其中插入值，然后使用 GETDATE()函数作为默认值生成所需的输出。

**注意–**
对于运行上述代码使用 SQL server 编译器，也可以使用在线编译器。

**应用:**
该功能用于返回数据库系统的当前日期和时间。