## SQL 日期函数

> 原文: [https://www.geeksforgeeks.org/sql-date-functions/](https://www.geeksforgeeks.org/sql-date-functions/)

在 SQL 中，日期对于新手来说很复杂，因为在使用数据库时，表中日期的格式必须与输入日期相匹配才能插入。在各种场景中，使用日期时间（时间也与日期相关）代替日期。

在 MySQL 中，默认的日期函数是：

### `NOW()`
返回当前日期和时间。

```sql
SELECT NOW();
```

输出：

```
2017-01-13 08:03:52
```

### `CURDATE()`
返回当前日期。

```sql
SELECT CURDATE();
```

输出：

```
2017-01-13
```

### `CURTIME()`
返回当前时间。

```sql
SELECT CURTIME();
```

输出：

```
08:05:15
```

### `DATE()`
提取日期或日期/时间表达式中的日期部分。

对于下表名为 `Test`：

| **Id** | **名称** | **出生时间** |
| :--- | :--- | :--- |
| 4120 | 我在练习 | 1996-09-26 16:44:15.581 |

```sql
SELECT Name, DATE(BirthTime) AS BirthDate FROM Test;
```

输出：

| **名称** | **生日** |
| :--- | :--- |
| 我在练习 | 1996-09-26 |

### `EXTRACT()`
返回日期/时间的单个部分。

语法：

```sql
EXTRACT(unit FROM date);
```

有几个单位可以考虑，但只使用了一些单位，如：`MICROSECOND`, `SECOND`, `MINUTE`, `HOUR`, `DAY`, `WEEK`, `MONTH`, `QUARTER`, `YEAR` 等。
`date` 是有效的日期表达式。

对于名为 `Test` 的下表：

| **Id** | **名称** | **出生时间** |
| :--- | :--- | :--- |
| 4120 | 我在练习 | 1996-09-26 16:44:15.581 |

**查询**

```sql
SELECT Name, EXTRACT(DAY FROM BirthTime) AS BirthDay FROM Test;
```

输出：

| **名称** | **生日** |
| :--- | :--- |
| 我在练习 | 26 |

```sql
SELECT Name, EXTRACT(YEAR FROM BirthTime) AS BirthYear FROM Test;
```

输出：

| **名称** | **出生年份** |
| :--- | :--- |
| 我在练习 | 1996 |

```sql
SELECT Name, EXTRACT(SECOND FROM BirthTime) AS BirthSecond FROM Test;
```

输出：

| **名称** | **出生第二次** |
| :--- | :--- |
| 我在练习 | 581 |

### `DATE_ADD()`
向日期添加指定的时间间隔。

语法：

```sql
DATE_ADD(date, INTERVAL expr type);
```

其中，`date` 是有效日期表达式，`expr` 是我们要添加的间隔数。
`type` 可以是以下之一：`MICROSECOND`, `SECOND`, `MINUTE`, `HOUR`, `DAY`, `WEEK`, `MONTH`, `QUARTER`, `YEAR` 等。

对于名为 `Test` 的下表：

| **Id** | **名称** | **出生时间** |
| :--- | :--- | :--- |
| 4120 | 我在练习 | 1996-09-26 16:44:15.581 |

**查询**

```sql
SELECT Name, DATE_ADD(BirthTime, INTERVAL 1 YEAR) AS BirthTimeModified FROM Test;
```

输出：

| **名称** | **出生时间修改** |
| :--- | :--- |
| 我在练习 | 1997-09-26 16:44:15.581 |

```sql
SELECT Name, DATE_ADD(BirthTime, INTERVAL 30 DAY) AS BirthDayModified FROM Test;
```

输出：

| **名称** | **生日修改** |
| :--- | :--- |
| 我在练习 | 1996-10-26 16:44:15.581 |

```sql
SELECT Name, DATE_ADD(BirthTime, INTERVAL 4 HOUR) AS BirthHourModified FROM Test;
```

输出：

| **名称** | **出生第二次** |
| :--- | :--- |
| 我在练习 | 1996-10-26 20:44:15.581 |

### `DATE_SUB()`
从日期中减去指定的时间间隔。`DATE_SUB` 的语法与 `DATE_ADD` 相同，不同的是 `DATE_SUB` 用于减去给定的日期间隔。

### `DATEDIFF()`
返回两个日期之间的天数。

语法：

```sql
DATEDIFF(date1, date2);
```
`date1` 和 `date2` 是日期/时间表达式。

示例：

```sql
SELECT DATEDIFF('2017-01-13','2017-01-03') AS DateDiff;
```

输出：

| **DateDiff** |
| :--- |
| 10 |

### `DATE_FORMAT()`
以不同格式显示日期/时间数据。

语法：

```sql
DATE_FORMAT(date, format);
```

`date` 是有效的日期，`format` 指定日期/时间的输出格式。可以使用的格式有：

*   `%a` - 缩写的星期名称（Sun - Sat）
*   `%b` - 缩写的月份名称（Jan - Dec）
*   `%c` - 月份，数字（0-12）
*   `%D` - 带英文后缀的一个月中的某一天（0th, 1st, 2nd, 3rd, ...）
*   `%d` - 月中的某一天，数字（00-31）
*   `%e` - 月中的某一天，数字（0-31）
*   `%f` - 微秒（000000-999999）
*   `%H` - 小时（00-23）
*   `%h` - 小时（01-12）
*   `%I` - 小时（01-12）
*   `%i` - 分钟，数字（00-59）
*   `%j` - 一年中的某一天（001-366）
*   `%k` - 小时（0-23）
*   `%l` - 小时（1-12）
*   `%M` - 月份名称（January - December）
*   `%m` - 月份，数字（00-12）
*   `%p` - AM 或 PM
*   `%r` - 时间，12 小时（hh:mm:ss 后跟 AM 或 PM）
*   `%S` - 秒（00-59）
*   `%s` - 秒（00-59）
*   `%T` - 时间，24 小时（hh:mm:ss）
*   `%U` - 周（00-53），其中周日是一周的第一天
*   `%u` - 周（00-53），其中星期一是一周的第一天
*   `%V` - 周（01-53），其中星期日是一周的第一天，与 `%X` 一起使用
*   `%v` - 周（01-53），其中星期一是一周的第一天，与 `%x` 一起使用
*   `%W` - 星期名称（Sunday - Saturday）
*   `%w` - 一周中的某一天（0 = Sunday，6 = Saturday）
*   `%X` - 周日是一周第一天的那一周的年份，四位数，与 `%V` 一起使用
*   `%x` - 周的年份，其中星期一是一周的第一天，四位数，与 `%v` 一起使用
*   `%Y` - 年份，数字，四位数
*   `%y` - 年份，数字，两位数

示例：

```sql
DATE_FORMAT(NOW(),'%d %b %y')
```

结果：

```
13 Jan 17
```

本文由 **[Pratik Agarwal](https://www.facebook.com/Pratik.Agarwal01)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。