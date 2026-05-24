# MAKETIME()和微秒()在 MariaDB 中

> 原文:[https://www . geeksforgeeks . org/make time-in-微秒马里亚数据库/](https://www.geeksforgeeks.org/maketime-and-microsecond-in-mariadb/)

**MAKETIME 函数:**
在 MariaDB 中，MAKETIME 函数用于返回某个小时、分钟、秒的时间组合。在这个函数中，第一个参数是小时，第二个参数是分钟，第三个参数是秒。该函数将返回小时、分钟和秒的组合。时间值的范围从“-838:59:59”到“838:59:59”。

**语法:**

```sql
MAKETIME( hour, minute, second )

```

**参数:**

| 参数 | 描述 |
| 小时 | 将用于创建时间的小时值。 |
| 分钟 | 将用于创建时间的分钟值。 |
| 第二 | 将用于创建时间的第二个值。 |

**返回:**
它会返回某个小时、分钟、秒的时间组合。

**示例–**

```sql
SELECT MAKETIME(9, 49, 15);

```

**输出:**

```sql
'09:49:15'

```

**示例–**

```sql
SELECT MAKETIME(23, 59, 59);

```

**输出:**

```sql
'23:59:59'

```

**示例–**

```sql
SELECT MAKETIME(-838, 59, 59);

```

**输出:**

```sql
'-838:59:59'

```

**微秒函数:**
在马里亚数据库中，微秒函数用于返回日期值的微秒部分。在这个函数中，第一个参数是 date_value。该函数将返回日期值的微秒部分。该函数返回给定日期值的微秒部分(0 到 999999 之间的数字)。

**语法:**

```sql
MICROSECOND( date_value )

```

**参数–**

| 因素 | 描述 |
| 日期值 | 从中提取微秒的时间或日期时间值。 |

**返回:**
微秒

**示例–**

```sql
SELECT MICROSECOND('2017-01-29 03:22:05.000001');

```

**输出:**

```sql
1
```

**示例–**

```sql
SELECT MICROSECOND('2017-07-15');

```

**输出:**

```sql
0
```

**示例–**

```sql
SELECT MICROSECOND('10:16:06.294675');

```

**输出:**

```sql
294675

```